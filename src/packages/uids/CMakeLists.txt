option(PACKAGE_UIDS "uids package" ON)

set(AUTO_SETEUID ON)
set(AUTO_TRUST_BACKBONE OFF)
if(${PACKAGE_UIDS})
    add_library(package_uids STATIC
            "uids.cc"
            "uids.h"
            )
    if(AUTO_SETEUID)
        target_compile_definitions(package_uids PUBLIC "AUTO_SETEUID")
    endif()
    if(AUTO_TRUST_BACKBONE)
        target_compile_definitions(package_uids PUBLIC "AUTO_TRUST_BACKBONE")
    endif()
endif()