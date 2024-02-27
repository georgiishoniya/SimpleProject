# CMakeList.txt: проект CMake для SimpleProject; включите исходный код и определения,
# укажите здесь логику для конкретного проекта.
#

# Добавьте источник в исполняемый файл этого проекта.
add_executable (SimpleProject "prime.cpp" "prime.h")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET SimpleProject PROPERTY CXX_STANDARD 20)
endif()

# TODO: Добавьте тесты и целевые объекты, если это необходимо.
target_link_libraries(SimpleProject primelib)