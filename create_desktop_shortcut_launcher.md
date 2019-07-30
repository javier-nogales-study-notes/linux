# Custom desktop file to launch a program graphically. 

1. Create The File:
  -The .desktop entries for your user account are stored at ~/.local/share/applications. cd into that directory, and have a look 
  around. You'll probably see a few files already in there. 
2. First line:
  -On the first line of the file, begin the block for a desktop entry. It should look like this:
  [Desktop Entry] 
3. Content:
  3.1. Basic info:
    -Name: Program name.
    -StartupWMClass: Every X window has it's own class for identification purposes. (!)-> All windows with the same class are 
                     grouped together.
    -Comment: When you mouse over launchers in most desktops, a small dialog box will appear with a short description of the 
              program. 
    -GenericName: Most desktops also support generic names for programs. These usually just say what the program is.
  3.2. Execution:
    -Exec: The command should really just point to the executable file that you want to run with the launcher and include any 
           options that you want to pass when it's run. If you were to copy that command into the terminal and run it, the browser 
           would open. That's exactly the behavior that you're looking for. 
  3.3. Icons:
    -Icon: Launcher path image, PNGs with a transparent background work best.
  3.4. Type And Catagories
    The type and categories values tell any menus where to place your launcher. The type tells the desktop environment if the 
    desktop entry is for an application, link, or directory. The categories value lets it know which categories to place your 
    launcher under. For a full list  of categories that desktop environments recognize, check the offical specification. 
    https://standards.freedesktop.org/menu-spec/latest/apa.html
    -Type: Program type, application;
    -Category: Program category, network;webBrowser;
  3.5. MIME Types
    MIME types tell the desktop environment which files to associate with the application. These are organized by category, then 
    by extension. You can have as many as you like. 
      Posible values(text/html;text/xml;application/xhtml+xml;application/xml;application/vnd.mozilla.xul+xml;
      application/rss+xml;application/rdf+xml;image/gif;image/jpeg;image/png;x-scheme-handler/http;x-scheme-handler/https;)
    -MimeType: Mime type of files which associate with the application.
  3.6. Keywords
    Keywords aren't that important. They're additional metadata that a desktop environment or its utilities can use to search for 
    your entry. They sort of extend the Name and GenericName values, giving you more words to associate with your application.
    -Keywords= Metadata to search for entry.
    
4. Full code template:
[Desktop Entry] 
Name=
StartupWMClass=
Comment=
GenericName=
Exec=
Icon=
Type=
Category=
MimeType=
Keywords=
