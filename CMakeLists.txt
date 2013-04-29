# Copyright (C) 2007-2012 LuaDist.
# Created by Peter Drahoš, David Manura
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( lua-ev C )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )
include ( lua )
include ( FindPackageHandleStandardArgs )
  
find_library ( EV_LIBRARY NAMES ev )
find_file ( EV_INCLUDE_DIR ev.h 
  PATH_SUFFIXES include/ev include
)

include_directories ( ${EV_INCLUDE_DIR} )

install_lua_module ( ev lua_ev.c ev.def LINK ${EV_LIBRARY} )

install_data ( README )
install_test ( test/ )
