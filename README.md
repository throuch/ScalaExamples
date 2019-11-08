# ScalaExamples

Une fonction qui renvoie le min et le max d'une liste de nombre en un seul parcourt.


```
val listeDeNombre : List[Int] = List(1)
val (min, max) = listeDeNombre.tail.foldLeft( (listeDeNombre(0), listeDeNombre(0))) ( (minmax, elem) => ( if (elem < minmax._1) elem  else minmax._1 , if (elem > minmax._2) elem else minmax._2))
```
