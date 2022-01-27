# KotlinObservable

## Parameters
 - initialValue - the initial value of the property.

 - onChange - the callback which is called after the change of the property is made. The value of the property has already been changed when this callback is invoked.

```
inline fun <T> observable(
    initialValue: T,
    crossinline onChange: (property: KProperty<*>, oldValue: T, newValue: T) -> Unit
): ReadWriteProperty<Any?, T>
```

### Example

```
var observed = false
var max: Int by Delegates.observable(0) { property, oldValue, newValue ->
    observed = true
}

println(max) // 0
println("observed is ${observed}") // false

max = 10
println(max) // 10
println("observed is ${observed}") // true
```
