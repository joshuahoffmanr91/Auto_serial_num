:: Joshua Hoffman 6/14/2018 ::

@echo off

echo --------------------------------------------------------
set /p SNPRFX="Enter SN prefix: "
echo --------------------------------------------------------
echo "SN prefix will be %SNPRFX%"
echo --------------------------------------------------------
set /p SCOUNT="Enter the starting number of the SNs to be generated: "
echo --------------------------------------------------------
echo SN generation will start at %SCOUNT%
echo --------------------------------------------------------
set /p TCOUNT="Enter the ending number of the SNs to be generated: "
echo --------------------------------------------------------
echo SN generation will end at %TCOUNT%
echo --------------------------------------------------------
set /p NCOUNT="Enter the length of the SN (max 10): "
echo --------------------------------------------------------
echo SN will be %NCOUNT% char in length
echo --------------------------------------------------------

setlocal EnableDelayedExpansion

if exist "build-SN - av2015.bat" (
    del "build-SN - av2015.bat" 
)

for /L %%i in (%SCOUNT%, 1, %TCOUNT%) do (
     set "PDVL=0000000000%%i"
     echo @av2009_pgmupd.exe av2009_bootloader_jtagoff.hex %SNPRFX%!PDVL:~-%NCOUNT%!.hex serial '%SNPRFX%!PDVL:~-%NCOUNT%!' >> "build-SN - av2015.bat"
)

echo Complete, hit a key to exit.
echo --------------------------------------------------------

pause>nul
