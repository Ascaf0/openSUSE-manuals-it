==An attempt to translate ''openSUSE official manuals'' to Italian language==

Files are taken from http://doc.opensuse.org/documentation/src/openSUSE/opensuse-manuals_12.2_src_en.tar.bz2, in order to start translating please download and untar it.
We are currently translating xml files for Start-up guide. Files untranslated are suffixed en.xml, when you translate a file please remove the "en." (e.g.: mv/cp filename.en.xml filename.xml).
Directories under images are currently empty (to save space on server). If you translate one of those images (and other files) -naturally if some translating is needed- found under opensuse-manuals_12.2_src_en/images, please upload the translated version to the corresponding location under opensuse-manuals_12.2_src_it/images.

Some sources and inspiration for translating tasks (in random order):

http://www.istitutomajorana.it/scarica2/OpenSuse_12-1_guida_italiana_completa.zip

http://ftp.hosteurope.de/mirror/ftp.opensuse.org/discontinued/SL-10.1/inst-source/suse/src/suselinux-manual_it-10.1-4.src.rpm

more...

==How to contribute==

Just fork and pull request or drop a message.

===How to proceed===

Just edit the xml file of your choice (actually docbook formatted) with your favorite editor OR convert that file to a translation catalog .pot file. Finally translate the .po file from en to it using some powerful translation tool like poedit, lokalize, virtaal, etc. Then revert to xml format.
In brief --if you want to follow this second path-- having installed package xml2pot, the flow is the following:

en.xml --(xml2pot)--> pot --("msginit --locale en --input file.pot --output file.po" or open with virtaal)--> it.po --(po2xml)--> .xml (with Italian-translated parts)

===With xml2po===

xml2po -l it -k -o 1_click_install_i.it.po 1_click_install_i.en.xml
lokalize 1_click_install_i.it.po
xml2po -l it -k -o 1_click_install_i.xml -p 1_click_install_i.it.po 1_click_install_i.en.xml

==With xml2pot===

xml2pot 1_click_install_i.en.xml > 1_click_install_i.pot
msginit --locale it --no-wrap --input 1_click_install_i.pot --output 1_click_install_i.it.po
lokalize 1_click_install_i.it.po
po2xml 1_click_install_i.en.xml 1_click_install_i.it.po > 1_click_install_i.xml

===Direct editing of file.xml===

This should be redundant...
cp myfile.en.xml myfile.xml
vi myfile.xml

Have fun!
