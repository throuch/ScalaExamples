# ScalaExamples

Une fonction qui renvoie le min et le max d'une liste de nombre en un seul parcourt.


```
val listeDeNombre : List[Int] = List(7, 1, 9, 4, 3, 9, 0, 2)
```

Première façon:
```
val (min, max) = listeDeNombre.tail.foldLeft((listeDeNombre(0), listeDeNombre(0))) 
               ((minmax, elem) => ( if (elem < minmax._1) elem else minmax._1, 
                                    if (elem > minmax._2) elem else minmax._2))
```

Deuxième façon plus élégante et performante:
```
val (min, max) = listeDeNombre.iterator.map(x => (x, x)).
        reduce((a, b) => (a._1 min b._1, a._2 max b._2))
```
