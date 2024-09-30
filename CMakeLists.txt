# Мінімально необхідна версія CMake
cmake_minimum_required(VERSION 3.29)

# Ім'я проекту
project(Task_2__Kursova_sys_prog)

# Встановлюємо стандарт C++ 20
set(CMAKE_CXX_STANDARD 20)

# Додаємо статичну бібліотеку "calculator" з файлу src/calculator.cpp
add_library(calculator STATIC src/calculator.cpp)

# Вказуємо директорію для заголовкових файлів (include)
target_include_directories(calculator PUBLIC ${PROJECT_SOURCE_DIR}/include)

# Додаємо виконуваний файл з файлу src/main.cpp
add_executable(Task_2__Kursova_sys_prog src/main.cpp)

# Зв'язуємо виконуваний файл з бібліотекою "calculator"
target_link_libraries(Task_2__Kursova_sys_prog calculator)

# Вказуємо CMake використовувати систему збірки Ninja
set(CMAKE_MAKE_PROGRAM "ninja")
