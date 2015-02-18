# Smart Parking Hello World

Smart Parking Hello World  is the easiest way to get started with writing your first Java Application that manages a parking lot for efficiency while receiving a stream of events from Magnetic sensors and Camera. 

You can get the [source code](https://github.com/Atomtion/SmartParkingHelloWorld) and create your own Smart Parking  Application with this [tutorial](http://tqldev.atomiton.com/docs)


## I. Requirements

SmartParkingHelloWorld requires JDK 1.7+ and Eclipse Version: Luna Service Release 1 (4.4.1) or other earlier versions.

#### II. Setting up your Eclipse Project

1. Generate the eclipse project settings files by running this script (for windows use gradlew.bat) : 
```
cd SmartParkingHelloWorld
./gradlew eclipse
```

2. Open the Eclipse and do File->Import->General->Existing Project into workspace.

3. Select your local SmartParkingHelloWorld folder as your root directory

4. SmartParkingHelloWorld project will now be loaded into Eclipse as a Java Project.


Finally, you can start modifying the code as appropriate - for example to receive events and
perform some business logic, post model updates etc .

#### III. Building from command line

1. You can build the application from command line as well by running this script (for windows use gradlew.bat) :
```
cd SmartParkingHelloWorld
./gradlew installApp
```

2. The executable script will be installed in the folder: 
```
build/install/SmartParkingHelloWorld/bin/SmartParkingHelloWorld
```

3. You can run the installed script from command line as follows:

```
build/install/SmartParkingHelloWorld/bin/SmartParkingHelloWorld <options>
```

#### IV. SmartParking HelloWorld Demonstrates Following Features

1. Get the Parking Lot Organization ID. This feature makes a simple HTTP GET call on the following URL as 
described in the documentation section. 

URL:  http://tqldev.atomiton.com:8080/fid-smartparking

Parameters: "Command=readAll&Model=Organization"

The response JSON is:
```json
{
    "Type": "ParkingLot.ParkingLotAssets.Organization",
    "Format": "version,timestamp",
    "Key": "Organization",
    "Organization": {
        "AddressStreetName1": {
            "Version": 2,
            "Timestamp": 1424117577573,
            "Value": "Mission & 4th"
        },
        "id": {
            "Version": 2,
            "Timestamp": 1424117577573,
            "Value": "Atom-Org-1" <<<---------------------ID Of the Organization
        },
        "LocLon": {
            "Version": 2,
            "Timestamp": 1424117577573,
            "Value": 88.1212
        },
        "Name": {
            "Version": 2,
            "Timestamp": 1424117577573,
            "Value": "Atomiton Smart Parking"
        },
        "LocLat": {
            "Version": 2,
            "Timestamp": 1424117577573,
            "Value": -122.1212
        },
        "Email": {
            "Version": 2,
            "Timestamp": 1424117577573,
            "Value": "parking@atomiton.com"
        },
        "sid": "JOKALN3FAAAH6AABAH5NXIXA"
    }
}
```
You can run the following command to see the output.
```
build/install/SmartParkingHelloWorld/bin/SmartParkingHelloWorld getOrgs
```

2.Get the Initial Parking Lot Snapshot and display various Ids associated with the parking lot - example: Floor, Parking Spots



3.Recieve the magnetic sensor and camera events.

4.Update the Area Light intensity. This example can be used to update other things in the parking lot like, Digital Sign, Parking Meter

