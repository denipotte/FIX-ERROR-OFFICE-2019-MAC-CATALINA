# Corrigir erro ao abrir office no OSX CATALINA 
    
    1 - Liberar aplicativos no Gatekeeper
            sudo spctl --master-disable
    
    2 - Acessar System Preferences >> Security & Privacy >> Allow apps downloaded from: Anywhere

    *** OPCIONAL ***
    3 - Se não fucnionar o comando acima forceAdd an app to quarantine on MacOS Catalina
            sudo xattr -rd com.apple.quarantine /Applications/XXXXXXXX.app
    ****************
    
    4 - Sign .app with Codesign
            xcode-select --install
            codesign --force --deep --sign - /Applications/Microsoft\ Word.app 
            codesign --force --deep --sign - /Applications/Microsoft\ Excel.app
            codesign --force --deep --sign - /Applications/Microsoft\ PowerPoint.app
            codesign --force --deep --sign - /Applications/Microsoft\ Outlook.app

Referência: https://kubadownload.com/news/codesign-sign-app/
