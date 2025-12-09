cmake_minimum_required(VERSION 3.16)
project(HolaMundoAdwaita C)

set(CMAKE_C_STANDARD 11)

# Activar pkg-config
find_package(PkgConfig REQUIRED)

# Buscar GTK4 + Libadwaita
pkg_check_modules(ADWAITA REQUIRED IMPORTED_TARGET libadwaita-1)

# Crear el ejecutable
add_executable(hola_mundo main.c)

# Enlazar automáticamente todas las includes + libs
target_link_libraries(hola_mundo PRIVATE PkgConfig::ADWAITA)
