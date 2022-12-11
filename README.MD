# Home Automation using Node MCU & Blynk Android App

> This is a whole new project which I'm working one  
> This is an IoT project which is automating the light bulbs and other parts of a house  


# Pre-requisites

> 1. Node MCU (ESP 8266)
> 2. Relay module
> 3. Blynk Android App
> 4. Bread board
> 5. Jump wires


# Steps to produce

I'm not gonna teach you steps on how to do. Everything is present in [this link](https://srituhobby.com/how-to-make-a-home-automation-system-using-the-nodemcu-esp8266-board-and-the-new-blynk-app/).


# Code

```
//Include the library files
#define BLYNK_PRINT Serial
#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266.h>

//Define the relay pins
#define relay1 D0
#define relay2 D1

#define BLYNK_AUTH_TOKEN "" //Enter your blynk auth token

char auth[] = BLYNK_AUTH_TOKEN;
char ssid[] = "ANONYMOUS";//Enter your WIFI name
char pass[] = "P@$$Nw0rD";//Enter your WIFI password

//Get the button values
BLYNK_WRITE(V0) {
  bool value1 = param.asInt();
  // Check these values and turn the relay1 ON and OFF
  if (value1 == 1) {
    digitalWrite(relay1, LOW);
  } else {
    digitalWrite(relay1, HIGH);
  }
}

//Get the button values
BLYNK_WRITE(V1) {
  bool value2 = param.asInt();
  // Check these values and turn the relay2 ON and OFF
  if (value2 == 1) {
    digitalWrite(relay2, LOW);
  } else {
    digitalWrite(relay2, HIGH);
  }
}

void setup() {
  //Set the relay pins as output pins
  pinMode(relay1, OUTPUT);
  pinMode(relay2, OUTPUT);

  // Turn OFF the relay
  digitalWrite(relay1, HIGH);
  digitalWrite(relay2, HIGH);

  //Initialize the Blynk library
  Blynk.begin(auth, ssid, pass, "blynk.cloud", 80);
}

void loop() {
  //Run the Blynk library
  Blynk.run();
}
```


# Images

> 1. Node MCU fully prepared


> 2. Relay Module fully prepared


> 3. Working of this project



# Author


|                                                                                                                                                                                                         <a href="https://nitin-kr.onrender.com/"><img src="https://github.com/nitinkumar30/nitscv/blob/main/image/nitin-1.jpg" width="150px " height="150px" /></a>                                                                                                                                                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|                                                                                                                                                                                                                                                                 **[Nitin Kumar](https://nitin-kr.onrender.com/)**                                                                                                                                                                                                                                                                  |
| <a href="https://twitter.com/nitinkumar30"><img src="https://raw.githubusercontent.com/vinitshahdeo/Water-Monitoring-System/master/assets/twitter.png" width="32px" height="32px"></a> <a href="https://www.facebook.com/b1AcK6AG16"><img src="https://raw.githubusercontent.com/vinitshahdeo/Water-Monitoring-System/master/assets/facebook.png" width="32px" height="32px"></a> <a href="https://www.linkedin.com/in/nitin30kumar/"><img src="https://raw.githubusercontent.com/vinitshahdeo/Water-Monitoring-System/master/assets/linkedin.png" width="32px" height="32px"></a> |


