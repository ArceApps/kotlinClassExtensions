# Kotlin ClassExtensions

```kotlin
class Extensions {

    fun Any?.isNull() : Boolean {
        return this == null
    }

    fun String.removeFirstLastChar() : String {
         return this.substring(1, this.length -1)
    }

    fun String.countSpaces(): Int {
        return this.count { count -> count == ' ' }
    }

    fun Activity.showToast(text : String, duration : Int = Toast.LENGTH_LONG) {
        Toast.makeText(this, text, duration).show()
    }

    fun Activity.color(@ColorRes color : Int) {
        ContextCompat.getColor(this, color)
    }

    fun EditText.onTextChanged(listener : (String) -> Unit) {
        this.addTextChangedListener(object : TextWatcher {
            override fun afterTextChanged(p0: Editable?) {
                //Se ha añadido un nuevo caracter al edit text
                listener(p0.toString())
            }

            override fun beforeTextChanged(p0: CharSequence?, p1: Int, p2: Int, p3: Int) {
                //Se va a añadir un nuevo caracter al edit text
            }

            override fun onTextChanged(p0: CharSequence?, p1: Int, p2: Int, p3: Int) {
                //Ya se ve el caracter en el edit text
            }
        })
    }
}
```
