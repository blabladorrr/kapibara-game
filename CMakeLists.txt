#cmake_minimum_required(VERSION 3.5)
#
#project (kapibara-game)
#
#set(SOURCES main.cpp)
#
#include_directories(SDL2Test ${SDL2_INCLUDE_DIRS})
#
## Add an executable with the above sources
#
#link_directories(/usr/local/lib/cmake/SDL2)
#add_executable(${PROJECT_NAME} ${SOURCES})
#
#target_link_libraries(${PROJECT_NAME} SDL2 SDL2_mixer)

cmake_minimum_required(VERSION 3.5)

# Set the project name
project (kapibara-game)

find_package(SDL2 REQUIRED)
# Create a sources variable with a link to all cpp files to compile
set(SOURCES main.cpp core/game.h core/game.cpp render/render.h render/render.cpp objects/player.h objects/player.cpp)

# Add an executable with the above sources
add_executable(${PROJECT_NAME} ${SOURCES})

target_link_libraries(kapibara-game ${SDL2_LIBRARIES})

# Set the directories that should be included in the build command for this target
include_directories(SDL2Test ${SDL2_INCLUDE_DIRS})
