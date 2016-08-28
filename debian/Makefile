DESTDIR =

TARGETDIR = $(DESTDIR)/usr/share/php/libzend-framework-php/
DOCPATH   = $(DESTDIR)/usr/share/doc/libzend-framework-php/
BINDIR	  = $(DESTDIR)/usr/bin/
ZF_PHP_DIR= $(DESTDIR)/usr/share/zend-framework/


LIBS = $(wildcard library/Zend/*)
TOPFILES  = $(wildcard *.md *.txt)

install-framework:
	install -d -o www-data -m 755 $(TARGETDIR)/

	cp -r library/Zend $(TARGETDIR)/
	chown -Rf www-data:www-data $(TARGETDIR)/Zend

	find $(TARGETDIR)/ -type f -exec chmod 644 {} \;

	install -d -m 755 $(DOCPATH)/
	install -m 644 $(TOPFILES) $(DOCPATH)/
	cp -r demos $(DOCPATH)/
	cp -r tests $(DOCPATH)/

install-zendx:
	install -d -o www-data -m 755 $(TARGETDIR)/

	cp -r extras/library/ZendX $(TARGETDIR)/
	chown -Rf www-data:www-data $(TARGETDIR)/ZendX
	find $(TARGETDIR)/ -type f -exec chmod 644 {} \;



install-scripts:
	install -d -m 755 $(BINDIR)
	install -d -m 755 $(ZF_PHP_DIR)
	cp bin/zf.php $(ZF_PHP_DIR)
	cp bin/zf.sh $(BINDIR)

