cmake_minimum_required(VERSION 3.5)
project(qcar2)

# Find dependencies
find_package(ament_cmake REQUIRED)

# Install directories to share/${PROJECT_NAME}
# This will copy the FOLDERS (urdf, meshes, config) into the install space

install(DIRECTORY urdf meshes launch DESTINATION share/${PROJECT_NAME})

ament_package()