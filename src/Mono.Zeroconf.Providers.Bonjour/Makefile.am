ASSEMBLY_NAME = Mono.Zeroconf.Providers.Bonjour
ASSEMBLY = $(ASSEMBLY_NAME).dll

MONO_ZEROCONF_PROVIDERS_BONJOUR_SRC =  \
	../AssemblyInfo.cs \
	Mono.Zeroconf.Providers.Bonjour/BrowseService.cs \
	Mono.Zeroconf.Providers.Bonjour/Native.cs \
	Mono.Zeroconf.Providers.Bonjour/RegisterService.cs \
	Mono.Zeroconf.Providers.Bonjour/Service.cs \
	Mono.Zeroconf.Providers.Bonjour/ServiceBrowser.cs \
	Mono.Zeroconf.Providers.Bonjour/ServiceClass.cs \
	Mono.Zeroconf.Providers.Bonjour/ServiceError.cs \
	Mono.Zeroconf.Providers.Bonjour/ServiceErrorException.cs \
	Mono.Zeroconf.Providers.Bonjour/ServiceFlags.cs \
	Mono.Zeroconf.Providers.Bonjour/ServiceRef.cs \
	Mono.Zeroconf.Providers.Bonjour/ServiceType.cs \
	Mono.Zeroconf.Providers.Bonjour/TxtRecord.cs \
	Mono.Zeroconf.Providers.Bonjour/TxtRecordEnumerator.cs \
	Mono.Zeroconf.Providers.Bonjour/ZeroconfProvider.cs

SOURCES = $(MONO_ZEROCONF_PROVIDERS_BONJOUR_SRC)

if BUILD_MDNSRESPONDER

assemblydir = $(libdir)/mono-zeroconf
assembly_SCRIPTS = $(ASSEMBLY) $(ASSEMBLY).mdb $(ASSEMBLY).config

all: $(ASSEMBLY)

$(ASSEMBLY): $(top_builddir)/src/Mono.Zeroconf/Mono.Zeroconf.dll $(SOURCES)
	$(MCS) -debug -target:library -out:$@ -r:$< $(AVAHI_LIBS) $(SOURCES)

$(ASSEMBLY).mdb: $(ASSEMBLY)

endif

EXTRA_DIST = $(SOURCES) $(ASSEMBLY).config \
	Mono.Zeroconf.Providers.Bonjour.csproj
CLEANFILES = *.dll *.mdb
DISTCLEANFILES = *.pidb
MAINTAINERCLEANFILES = \
	Makefile.in

