xpGetExtern(externIncs externLibs PUBLIC boost wxWidgets)
include_directories(${externIncs} ${CMAKE_SOURCE_DIR})
add_subdirectory(PlayerAPI)
add_subdirectory(NetworkInterface)
add_subdirectory(GameLogic)
add_subdirectory(Messages)
add_subdirectory(AI)
add_executable(Server
main.cpp
Lobby.cpp
Lobby.hpp
)
add_library(ServerLib
Lobby.cpp
Lobby.hpp
)
target_link_libraries(Server
AI
NetworkInterface
Game
GameLogic
Messages
${externLibs})
