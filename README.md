# RFDuino
Tests and trials with BLE and the RFduino

##Test1
Run a single shift register off the RFduino. Below is the circuit diagram

##Test2
Run 2 shift registers. Below are the circuits and Service definition
####Service definition
        // create number
        BLEIntCharacteristic ledStripCharacteristic = BLEIntCharacteristic("FF12", BLERead | BLEWrite);
        BLEDescriptor ledStripDescriptor = BLEDescriptor("2901", "Number");
        // set advertised local name and service UUID
        blePeripheral.setLocalName("LEDStrip");
        blePeripheral.setDeviceName("LEDStrip");
        blePeripheral.setAdvertisedServiceUuid(ledService.uuid());
        
        // add service and characteristics
        blePeripheral.addAttribute(ledService);
        blePeripheral.addAttribute(ledStripCharacteristic);
        blePeripheral.addAttribute(ledStripDescriptor);
        
        // assign event handlers for characteristic
        ledStripCharacteristic.setEventHandler(BLEWritten, ledStripCharacteristicWritten);
        


##Final Aim
Create a photo display to which you can send a photo from your phone.
