# TestCase_67027169 Tesk_2

*** Settings ***
Library         SeleniumLibrary

*** Variables ***
${URL}          https://reg.up.ac.th/
${BROWSER}      Chrome
${USER}         67027169@up.ac.th
${PASS}         Di_diamond001

*** Test Cases ***
Login Student Success
    Open Browser    ${URL}    ${BROWSER}
    Maximize Browser Window
    Click Element    xpath=//a[contains(text(), 'เข้าสู่ระบบ')]
    Input Text      id=username    ${USER}
    Input Password  id=password    ${PASS}
    Click Button    id=login-button
    Wait Until Page Contains    67027169
    [Teardown]    Close Browser
