A prototype of HAR human activity classification was created on an IoT platform for a healthcare application.  Through inertial sensors, kinematic data are collected that are transferred to a convolutional neural network imported on the same board for the classification of activities. For an accurate identification of the patient's position, an ultrasound platform localization system has been associated. The IoT platform is an STM32L475VG board where multiple sensors are integrated including those of temperature, humidity, a digital barometer, a proximity sensor (ToF) and magnetometric sensor (accelerometer and gyroscope) as well as being equipped with a serial interface for communications.The microcontroller has a maximum frequency of 80 MHz, a flash memory of 1 Mbyte and an SRAM memory of 128 KByte. It is also equipped with different communication modules  (e.g. WIFI, BLE, NFC communication). It is also possible to use a wide embedded software platform for the design of the prototype. An Integrated Development Environment (IDE) was used for the implementation of the project. The start of the project requires the activation of all the components present on the board. This phase is carried out through the STM32 CubeMX FP (extension of STM32 Cube). Among the various setting functions required there is the initialization phase of the various sensors which is carried out with the X-Cube MEMS function. For the communication protocol "in the connectivity window" the I2C protocol is configured to enable the acquisition of data from the sensors. The data collected by the sensors is then fused by applying the Kalman filter and then sent to CNN. To implement the neural network in the project it has been used the X-Cube-AI tool.Expansion package of the STM32Cube. It´s a software configuration tool dedicated to Artificial Intelligence (AI) project development from the conception to the realization. It also includes STM32CubeProg, a programming tool.  X-Cube-AI provides an automatic neural network generator optimized in computation and memory (RAM and Flash) that converts pre-trained Neural Network from most used DL framework into a library automatically integrated into the user´s project. Therefore this tool has allowed us to extract from Keras Library a pre-trained CNN for HAR, to be converted into C code. The X-Cube-AI tool and converting the neural network model into C code validate the model on both the host and the target. The network created is a .h5 model generated with Keras library, HAR\_IGN\_WISDM trained on the public Wireless Sensor Data Mining. For the localization system an ultrasound network has been employed. An ultrasound network is used for localization. The data is transmitted via WIFI to the board.

Tools Required

The tools required are:

Keras 2. \*

Numpy

Matplotlib

Pandas     

For the development of the prototype some embedded software are required such as:

STM32CubeMX

X-CUBE-AI, expansion of STM32CubeMX

Data Acquisition 

I dati accelerometrici sono acquisiti tramite il sensore LSM6DSL che un system-in-package with a 3D digital accelerometer and 3D digital gyroscope with I2C/SPI interface for output communication. The accelerometric data are acquired through the LSM6DSL sensor which a system-in-package with a 3D digital accelerometer and 3D digital gyroscope with I2C / SPI interface for output communication. 

The data acquired after a pre-processing phase is sent to a neural network for a classification of downstairs, upstairs, walking, jogging and standing activities. The neural network used is a sequential CNN network produced directly on the system board by the Keras NN pre-trained library. The topology consists of: two convolutional layers, two pooling layers, two fully connected layers.  

Validation process

` `X-Cube-AI tool and converting the Neural Network model into C code validate the model on the host and target. 

Data Visualization 

Connecting a smartphone to STM32L475VG board via BLE and using the Android STBLE Sensor application you can view the data transmitted by the sensors.  



