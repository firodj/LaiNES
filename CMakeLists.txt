cmake_minimum_required(VERSION 3.20)

project(laines)

set (CMAKE_CXX_STANDARD 14)

set (SRC
  src/ppu.cpp
  src/mapper.cpp
  src/cartridge.cpp
  src/menu.cpp
  src/include/apu.hpp
  src/include/cpu.hpp
  src/include/gui.hpp
  src/include/joypad.hpp
  src/include/config.hpp
  src/include/menu.hpp
  src/include/mappers/mapper4.hpp
  src/include/mappers/mapper2.hpp
  src/include/mappers/mapper3.hpp
  src/include/mappers/mapper1.hpp
  src/include/mappers/mapper0.hpp
  src/include/common.hpp
  src/include/ppu.hpp
  src/include/mapper.hpp
  src/include/cartridge.hpp
  src/palette.inc
  src/gui.cpp
  src/joypad.cpp
  src/config.cpp
  src/mappers/mapper4.cpp
  src/mappers/mapper2.cpp
  src/mappers/mapper3.cpp
  src/mappers/mapper1.cpp
  src/apu.cpp
  src/cpu.cpp
  src/main.cpp
  lib/Nes_Oscs.cpp
  lib/Multi_Buffer.cpp
  lib/include/Nes_Apu.h
  lib/include/blargg_common.h
  lib/include/Nes_Vrc6.h
  lib/include/boost/static_assert.hpp
  lib/include/boost/config.hpp
  lib/include/boost/cstdint.hpp
  lib/include/Multi_Buffer.h
  lib/include/Nes_Oscs.h
  lib/include/apu_snapshot.h
  lib/include/Sound_Queue.h
  lib/include/Blip_Synth.h
  lib/include/Nes_Namco.h
  lib/include/Blip_Buffer.h
  lib/include/blargg_source.h
  lib/include/Nonlinear_Buffer.h
  lib/Nonlinear_Buffer.cpp
  lib/Nes_Apu.cpp
  lib/apu_snapshot.cpp
  lib/Blip_Buffer.cpp
  lib/Nes_Namco.cpp
  lib/Sound_Queue.cpp
  lib/Nes_Vrc6.cpp
)

include_directories(
  src/include
  lib/include
  simpleini
)

find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})

find_package(SDL2_image REQUIRED)
find_package(SDL2_ttf REQUIRED)
add_executable(laines ${SRC})
target_link_libraries(laines SDL2::SDL2 SDL2_image::SDL2_image SDL2_ttf::SDL2_ttf)

set_target_properties( laines
  PROPERTIES
  RUNTIME_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}"
)
