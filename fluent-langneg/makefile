PACKAGE := fluent-langneg
GLOBAL  := FluentLangNeg

include ../common.mk

build: $(PACKAGE).js compat.js

$(PACKAGE).js: $(SOURCES)
	@rollup $(CURDIR)/src/index.js \
	    --config $(ROOT)/bundle_config.js \
	    --banner "/* $(PACKAGE)@$(VERSION) */" \
	    --amd.id $(PACKAGE) \
	    --name $(GLOBAL) \
	    --output.file $@
	@echo -e " $(OK) $@ built"

compat.js: $(SOURCES)
	@rollup $(CURDIR)/src/index.js \
	    --config $(ROOT)/compat_config.js \
	    --banner "/* $(PACKAGE)@$(VERSION) */" \
	    --amd.id $(PACKAGE) \
	    --name $(GLOBAL) \
	    --output.file $@
	@echo -e " $(OK) $@ built"

clean:
	@rm -f $(PACKAGE).js compat.js
	@rm -rf .nyc_output coverage
	@echo -e " $(OK) clean"
