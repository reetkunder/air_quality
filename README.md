# air_quality

def ozone_reading = ozone / 8.0

        SO2_reading = SO2 / 20

        particles_reading = particles / 25



def get_non_negative_int(prompt):          

    while True:

        try:

            value = float(input(prompt))

        except ValueError:

            print("Please enter a nonnegative number")

            continue

 

        if value < 0:

            print("Please enter a nonnegative number")

            continue

        else:

            break

    return value

 

 

if __name__ == "__main__":              # Main Function

 

    while True:             # Reading the numbers of readings.

        try:

            read = int(input("Enter the number of readings: "))

        except ValueError:          # To handle the case if some non integer value is entered.

            print("Please enter a positive integer")

            continue

        if read <= 0:                # Input should be greater than 0

            print("Please enter a positive integer")

            continue

        else:

            break

 

    for i in range(read):       # To collect user inputs

 

        head = "Reading " + str(i+1)

        print("\n" + head)

 

        # User Inputs.

        ozone = get_non_negative_int("Amount of ozone recorded (parts per hundred million): ")

        SO2 = get_non_negative_int("Amount of sulfur dioxide recorded (parts per hundred million): ")

        particles = get_non_negative_int("Amount of particles less than 2.5 micrometres diameter recorded (micrograms per cubic metre): ")

 

        # Calculating the various AQI parameters

        

 

        if (ozone_reading >= SO2_reading) and (ozone_reading >= particles_reading):

            print("\n" + "AQI " + str(float(ozone_reading)*100))

        elif (SO2_reading >= ozone_reading) and (SO2_reading >= particles_reading):

            print("\n" + "AQI " + str(float(SO2_reading) * 100))

        else:

            print("\n" + "AQI " + str(float(particles_reading) * 100))

 
