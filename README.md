# GUESSING-NUMBER-GAME
CMD
@echo off
title Number Guessing Game
color 0A

set /a secret=%random% %% 100 + 1
set tries=0

echo ============================
echo    NUMBER GUESSING GAME
echo ============================
echo.
echo I have selected a number between 1 and 100.
echo Try to guess it!
echo.

:guess
set /a tries+=1
set /p user=Enter your guess: 

if %user%==%secret% goto win
if %user% GTR %secret% (
    echo Too High! Try again.
    echo.
    goto guess
)
if %user% LSS %secret% (
    echo Too Low! Try again.
    echo.
    goto guess
)

:win
echo.
echo 🎉 CONGRATULATIONS!
echo You guessed the correct number.
echo Total attempts: %tries%
echo.
pause
