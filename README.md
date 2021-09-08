open class Driver(var name: String, var age: Int = 0) {

open var drierAge = age

}

open class Vehicle(var driver: Driver ?= null) {



       open fun drive() {
        val d = driver
        if (d != null) {
            println("Car didn’t drive - there’s no driver")
            if(d.age >= 18) {
                println("")
            }
        }
}
}
var miles: Int = 0



class Car() : Vehicle() {


    var miles = 100
    override fun drive() {
        var d = driver
        if (d == null) {
            println("Car didn’t drive - there’s no driver")
        } else if (d.age >= 18) {
            println("Car drove 10 miles - ${miles - 10} miles to go")
            miles -= 10
        } else {
            println("Car didn't drive - ${d.name} is ${d.age}, but must be 18 or older to drive")
        }
    }
}


class MilitaryTank() : Vehicle() {

    var miles = 2000
    override fun drive() {
        var d = driver
        if (d == null) {
            println("MilitaryTank didn’t drive - there’s no driver")
        } else if (d.age >= 25) {
            println("MilitaryTank drove 5 miles - ${miles - 5} miles to go")
            miles -= 5
        } else {
            println("MilitaryTank didn't drive - ${d.name} is ${d.age}, but must be 25 or older to drive")
        }
    }
}

