# Car-Python-Lab
#!/usr/bin/env python3
#Johann Silvanus
#11/06/18
# A position tracking program for a car racing game

# A class to represent a car
class Car:
    def __init__(self, start_pos, speed):
        #1 from the lab, set internal class attributes
        self.start_pos = start_pos
        self.speed = speed

    def drive(self, time, direction):
        #2 from the lab, implement the method to move the car forward and backward
        self.time=time
        if direction == 'forward':
            self.start_pos += self.speed * self.time
        if direction == 'backward':
            self.start_pos -= self.speed * self.time

    def printPosition(self):
        # This prints the current position of the car
        print("The car is currently at position " + str(self.start_pos))

# Code to test your car
def main():
    # I instantiate one car and do some actions to test the class
    myCar = Car(2, 3)
    myCar.printPosition()
    myCar.drive(3, 'forward')
    myCar.printPosition()
    myCar.drive(2, 'backward')
    myCar.printPosition()

    # You must create a new instance of car here starting at position 0 with 
    # speed 4 and move it three times: First move it 5 forward, then 3 backward, 
    # then 6 forward. Be sure to print the position after creating the car
    # and again after each move

    newCar = Car(0,4)
    newCar.printPosition()
    newCar.drive(5, 'forward')
    newCar.printPosition()
    newCar.drive(3, 'backward')
    newCar.printPosition()
    newCar.drive(6, 'forward')
    newCar.printPosition()

# Calls the main function if the program isn't loaded as a module
if __name__ == "__main__":
    main()

