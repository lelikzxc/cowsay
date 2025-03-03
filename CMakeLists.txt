cmake_minimum_required(VERSION 3.10)
project(YetAnotherEducationalCowsay)

# Устанавливаем стандарт C++
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Добавляем исходные файлы
set(SOURCES
    ASCIIPicture.cpp
    Cloud.cpp
    Cow.cpp
    Field.cpp
    Parser.cpp
    main.cpp
)

# Добавляем заголовочные файлы
set(HEADERS
    ASCIIPicture.hpp
    Cloud.hpp
    Cow.hpp
    Field.hpp
    Parser.hpp
)

# Создаем исполняемый файл
add_executable(${PROJECT_NAME} ${SOURCES} ${HEADERS})

# Настройка флагов компиляции в зависимости от компилятора
if (CMAKE_CXX_COMPILER_ID STREQUAL "MSVC")
    target_compile_options(${PROJECT_NAME} PRIVATE /W4 /permissive-)
elseif (CMAKE_CXX_COMPILER_ID STREQUAL "GNU" OR CMAKE_CXX_COMPILER_ID STREQUAL "Clang")
    target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra -pedantic)
endif()
