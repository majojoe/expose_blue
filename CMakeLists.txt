cmake_minimum_required(VERSION 2.8.11)

project(ExposeBlue)

install(DIRECTORY ExposeBlue DESTINATION /usr/share/sddm/themes  )
install(FILES files/kde_settings.conf DESTINATION /etc/sddm.conf.d/ PERMISSIONS OWNER_READ OWNER_WRITE GROUP_READ WORLD_READ)
set(CPACK_PACKAGE_NAME "expose-blue")
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "sddm theme expose blue that provides a login theme that works well with users that are provided by AD servers.")
set(CPACK_PACKAGE_VERSION "1.0.2")
set(SYSTEM_ARCH "all")
set(CPACK_DEBIAN_PACKAGE_DEPENDS "sddm")
set(CPACK_GENERATOR "DEB")
set(PACKAGE_OS "linux")
set(CPACK_SYSTEM_NAME "${PACKAGE_OS}-amd64")
set(SYSTEM_ARCH "amd64")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "Johannes Maier <maier_jo@gmx.de>")
set(CPACK_DEBIAN_PACKAGE_CONTROL_EXTRA "${CMAKE_CURRENT_SOURCE_DIR}/postinst;${CMAKE_CURRENT_SOURCE_DIR}/prerm;${CMAKE_CURRENT_SOURCE_DIR}/postrm")
set(CPACK_PACKAGE_FILE_NAME "${CPACK_PACKAGE_NAME}-${CPACK_PACKAGE_VERSION}-${CPACK_DEBIAN_REVISON}${CPACK_SYSTEM_NAME}")

include(CPack)


