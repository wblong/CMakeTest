project(extension_test LANGUAGES CXX)

add_executable(extension_test test_ExtensionClass.cpp)

target_link_libraries(extension_test PRIVATE foo)

add_test(NAME extension_test COMMAND $<TARGET_FILE:extension_test>)

# 当创建动态库时，

# 如果源文件(例如CPP)中包含第三方头文件，但是头文件（例如hpp）中不包含该第三方文件头，采用PRIVATE。
# 如果源文件和头文件中都包含该第三方文件头，采用PUBLIC。
# 如果头文件中包含该第三方文件头，但是源文件(例如CPP)中不包含，采用 INTERFACE。
