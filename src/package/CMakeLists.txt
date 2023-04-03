cmake_minimum_required(VERSION 3.5)
project(package)

set(CXX_STANDARD 17)
set(CXX_STANDARD_REQUIRED on)

### Auto-generated
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

# Add executable
add_executable(publisher_node src/publisher.cpp)
ament_target_dependencies(publisher_node rclcpp std_msgs)

add_executable(subscriber_node src/subscriber.cpp)
ament_target_dependencies(subscriber_node rclcpp std_msgs)

# Install executable
install(TARGETS 
  publisher_node
  subscriber_node
  DESTINATION lib/${PROJECT_NAME})
  
# Install launch file
install(DIRECTORY 
  launch
  DESTINATION share/${PROJECT_NAME})

# Install package.xml
install(FILES 
  package.xml
  DESTINATION share/${PROJECT_NAME})

### Auto-generated
if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # comment the line when a copyright and license is added to all source files
  set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # comment the line when this package is in a git repo and when
  # a copyright and license is added to all source files
  set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()

