cmake_minimum_required(VERSION 3.22)

project(Arduino-FOC)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_C_STANDARD_REQUIRED ON)

add_library(Arduino-FOC
    src/BLDCMotor.cpp
    src/HybridStepperMotor.cpp
    src/StepperMotor.cpp
    src/common/foc_utils.cpp
    src/common/lowpass_filter.cpp
    src/common/pid.cpp
    src/common/time_utils.cpp
    src/common/base_classes/CurrentSense.cpp
    src/common/base_classes/FOCMotor.cpp
    src/common/base_classes/Sensor.cpp
    src/communication/Commander.cpp
    src/communication/SimpleFOCDebug.cpp
    src/current_sense/LowsideCurrentSense.cpp
    src/sensors/GenericSensor.cpp)

target_link_libraries(Arduino-FOC PRIVATE
    m
    Arduino
)

target_include_directories(Arduino-FOC PUBLIC src)
