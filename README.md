#! /usr/bin/env python3

class Car:
    def __init__(self, start_pos, speed, driver):
        self.start_pos = start_pos
        self.speed = speed
        self.driver = driver

    def drive(self, time, direction):
        self.time=time
        if direction == 'forward':
            self.start_pos += self.speed * self.time
        if direction == 'backward':
            self.start_pos -= self.speed * self.time

    def printPosition(self):
        print("The car is currently at position " + str(self.start_pos))

    def setDriver(self, driver):
        self.driver = driver

    def getDriver(self):
        return self.driver

class driver:
    def __init__(self, name, age, licenseType, wears_seatbelt):
        self.name = name
        self.age = age
        self.licenseType = licenseType
        self.wears_seatbelt = wears_seatbelt
        bool(self.wears_seatbelt)

    def setName(self, name):
        self.name = name

    def setAge(self, age):
        self.age = age

    def setLicenseType(self, licenseType):
        self.licenseType = licenseType

    def getName(self):
        return self.name

    def getAge(self):
        return self.age

    def getLicenseType(self):
        return self.licenseType

    def printName(self):
        print("The driver's name is " + self.name)

    def toggleSeatbelt(self):
        if self.wears_seatbelt == True:
            self.wears_seatbelt == False
        else:
            self.wears_seatbelt == True

class raceCar(Car):
    def __init__(self, start_pos, speed, driver, top_speed):
        self.top_speed = top_speed
        super().__init__(start_pos, speed, driver)
        

    def atTopSpeed(self):
        if self.speed >= self.top_speed:
            return True

    def drive(self, time, direction):
        if not self.atTopSpeed() or time <= 3:
            super().drive(time, direction)

        else:
            print("Overheating, cannot move.")

        if self.driver.wears_seatbelt == True:
            super().drive(time, direction)

        else:
            print("Wear a seatbelt!")

def main():
    myDriver = driver("Tom", 21, "Full", True)
    myCar = raceCar(2, 3, myDriver, 5)
    myCar.getDriver().printName()
    myCar.printPosition()
    myCar.drive(3, 'forward')
    myCar.printPosition()
    myCar.drive(2, 'backward')
    myCar.printPosition()

if __name__ == "__main__":
    main()
