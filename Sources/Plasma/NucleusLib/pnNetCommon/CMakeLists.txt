include_directories("../../CoreLib")
include_directories("../../NucleusLib")
include_directories("../../NucleusLib/inc")
include_directories("../../PubUtilLib")

set(pnNetCommon_HEADERS
    plCreatableUuid.h
    plGenericVar.h
    plNetAddress.h
    plNetApp.h
    plNetGroup.h
    plNetServers.h
    plNetSharedState.h
    plSDLTypes.h
    plSynchedObject.h
    plSynchedValue.h
    pnNetCommon.h
    pnNetCommonCreatable.h
)

set(pnNetCommon_SOURCES
    plGenericVar.cpp
    plNetAddress.cpp
    plNetApp.cpp
    plNetGroup.cpp
    plNetServers.cpp
    plNetSharedState.cpp
    plSDLTypes.cpp
    plSynchedObject.cpp
    plSynchedValue.cpp
    pnNetCommon.cpp
)

add_library(pnNetCommon STATIC ${pnNetCommon_HEADERS} ${pnNetCommon_SOURCES})
target_link_libraries(pnNetCommon pnNucleusInc)
target_link_libraries(pnNetCommon pnDispatch)
target_link_libraries(pnNetCommon pnFactory)
target_link_libraries(pnNetCommon pnKeyedObject)
target_link_libraries(pnNetCommon pnUUID)
if(WIN32)
    target_link_libraries(pnNetCommon ws2_32)
endif(WIN32)

source_group("Header Files" FILES ${pnNetCommon_HEADERS})
source_group("Source Files" FILES ${pnNetCommon_SOURCES})
