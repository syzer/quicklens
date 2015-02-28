Quicklens
=========

Modify deeply nested fields in case classes, e.g.:

````scala
case class Street(name: String)
case class Address(street: Street)
case class Person(address: Address)

val person = Person(Address(Street("1 Functional Rd.")))

modify(person)(_.address.street.name).using(_.toUpperCase)
````

Similar to lenses ([1](http://eed3si9n.com/learning-scalaz/Lens.html),
[2](https://github.com/julien-truffaut/Monocle)), but without the actual lens creation.

Read [the blog](http://www.warski.org/blog/2015/02/quicklens-modify-deeply-nested-case-class-fields/) for more info.