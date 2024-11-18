# plp-python-week-5
Assignment 1: Design Your Own Class! 🏗️
Create a class representing anything you like (a Smartphone, Book, or even a Superhero!).
Add attributes and methods to bring the class to life!
Use constructors to initialize each object with unique values.
Add an inheritance layer to explore polymorphism or encapsulation.


class Smartphone:
    def __init__(self, brand, model, storage, battery_life):
        self.brand = brand
        self.model = model
        self.storage = storage
        self.battery_life = battery_life

    def make_call(self, number):
        return f"Calling {number} from {self.brand} {self.model}."

    def send_message(self, number, message):
        return f"Sending message to {number}: {message}"

    def get_specs(self):
        return f"{self.brand} {self.model} - Storage: {self.storage}GB, Battery Life: {self.battery_life} hours"


class SmartphoneWithCamera(Smartphone):
    def __init__(self, brand, model, storage, battery_life, camera_megapixels):
        super().__init__(brand, model, storage, battery_life)
        self.camera_megapixels = camera_megapixels

    def take_photo(self):
        return f"Taking a photo with {self.camera_megapixels}MP camera."

    def get_specs(self):
        base_specs = super().get_specs()
        return f"{base_specs}, Camera: {self.camera_megapixels}MP"


# Example usage
smartphone = Smartphone("Apple", "iPhone 14", 128, 20)
print(smartphone.make_call("123-456-7890"))
print(smartphone.get_specs())

camera_phone = SmartphoneWithCamera("Samsung", "Galaxy S21", 256, 22, 108)
print(camera_phone.take_photo())
print(camera_phone.get_specs())


Activity 2: Polymorphism Challenge! 🎭

Create a program that includes animals or vehicles with the same action (like move()). However, make each class define move() differently (for example, Car.move() prints "Driving" 🚗, while Plane.move() prints "Flying" ✈️).

class Vehicle:
    def move(self):
        raise NotImplementedError("Subclasses must implement this method")


class Car(Vehicle):
    def move(self):
        return "Driving 🚗"


class Plane(Vehicle):
    def move(self):
        return "Flying ✈️"


class Bicycle(Vehicle):
    def move(self):
        return "Pedaling 🚲"


# Example usage
vehicles = [Car(), Plane(), Bicycle()]

for vehicle in vehicles:
    print(vehicle.move())
