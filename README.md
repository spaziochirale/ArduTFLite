# ArduTFLite
## TensorFlow Lite Micro Library in Arduino Style

This library simplifies the use of **TensorFlow Lite Micro** on Arduino boards, offering APIs in the typical _Arduino style_. It avoids the use of _pointers_ or other C++ syntactic constructs that are discouraged within an Arduino sketch.

**ArduTFLite** serves as a wrapper for the _Chirale_TensorFlowLite library_, which is a port of the official TensorFlow Lite Micro library for Arduino boards with ARM and ESP32 architecture.

**ArduTFLite** is designed to enable experimentation with **Tiny Machine Learning** on Arduino boards with greater resources, such as **Arduino Nano 33 BLE**, **Arduino Nano ESP32**, **Arduino Nicla**, and **Arduino Portenta**. It allows even those without extensive TensorFlow expertise to use it without needing to fine tune the *TensorFlow Lite interpreter*.

## Installation

The library can be installed from the Arduino IDE Library Manager or can be installed as .zip file downloaded from this GitHub repository.
The library depends on the Chirale_TensorFlowLite library.

## Usage examples

The examples included with the library show how to use the library. The examples include a pre-trained model.

## General Usage Guide:

1. **Create an Arduino Sketch to collect data suitable for training**: First, create an Arduino sketch to collect data to be used as the training dataset.
2. **Define the DNN model**: Once the training dataset is acquired, create a neural network model using a TensorFlow development environment, such as Google Colaboratory.
3. **Train the Model**: Train the model on the training data.
4. **Convert and Save the Model**: Convert the trained model to TensorFlow Lite format and save it as a `model.h` file. This file should contain the definition of a static byte array corresponding to the binary format (flat buffer) of the TensorFlow Lite model.
5. **Create the Arduino Sketch for Inference**

1. **Include Necessary Headers**: Include the `ArduTFLite.h` header file and the `model.h` file.
2. **Define Tensor Arena**: Define a globally sized byte array for the area called tensorArena.
3. **Initialize the Model**: Initialize the model using the `modelInit()` function.
4. **Set Input Data**: Insert the input data into the model's input tensor using the `modelSetInput()` function.
5. **Run Inference**: Invoke the inference operation using the `modelRunInference()` function.
6. **Read Output Data**: Read the output data using the `modelGetOutput()` function.

