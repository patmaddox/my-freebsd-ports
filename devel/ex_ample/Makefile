PORTNAME= ex_ample
CATEGORIES= devel

USE_LOCALE= en_US.UTF-8

NO_CHECKSUM= yes
BUILD_DEPENDS= elixir>=1.13.4:lang/elixir

USE_GITHUB= yes
GH_ACCOUNT= patmaddox
GH_TAGNAME= dafb22e40a66647869ae13e55d2980734fa4f25a

MIX_ENV= prod

do-build:
	cd $(WRKSRC) && MIX_ENV=$(MIX_ENV) LANG="$(USE_LOCALE)" LC_ALL="$(USE_LOCALE)" mix release

do-install:
	mkdir -p $(STAGEDIR)$(PREFIX)/libexec/$(PORTNAME)
	cp -R $(WRKSRC)/_build/$(MIX_ENV)/rel/$(PORTNAME)/ $(STAGEDIR)$(PREFIX)/libexec/$(PORTNAME)
	ln -s $(PREFIX)/libexec/$(PORTNAME)/bin/$(PORTNAME) $(STAGEDIR)$(PREFIX)/bin/$(PORTNAME)
	cd $(STAGEDIR)$(PREFIX) && find * -type f -or -type l >> $(TMPPLIST)

.include <bsd.port.mk>
