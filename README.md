# MS5607-NonBlocking
A non-blocking library for the MS5607. 
Based on the library by Uravu Labs: https://github.com/UravuLabs/MS5607

Accompanying Youtube Video: https://www.youtube.com/watch?v=5dGfKoYblQE


## Example usage:


``` cpp
float altitude;

MS5607 myAltimeter(&altitude);

void setup(){
    Serial.begin(9600);
    myAltimeter.begin();
}

void loop(){
    if(myAltimeter.handleAltimeter() == 1){
        Serial.println(altitude);
    }
}
```


- Make sure to initialize MS5607 class with the address of your altitude variable
- handleAltimeter equals 1 when conversion of data is ready and new altitude is ready
- It equals 0 when there is no new altitude yet.
