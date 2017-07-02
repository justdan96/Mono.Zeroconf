ASSEMBLY_NAME = Mono.Zeroconf
ASSEMBLY = $(ASSEMBLY_NAME).dll

MONO_ZEROCONF_SRC =  \
	../AssemblyInfo.cs \
	Mono.Zeroconf.Providers/IZeroconfProvider.cs \
	Mono.Zeroconf.Providers/ProviderFactory.cs \
	Mono.Zeroconf.Providers/ZeroconfProviderAttribute.cs \
	Mono.Zeroconf/AddressProtocol.cs \
	Mono.Zeroconf/IRegisterService.cs \
	Mono.Zeroconf/IResolvableService.cs \
	Mono.Zeroconf/IService.cs \
	Mono.Zeroconf/IServiceBrowser.cs \
	Mono.Zeroconf/ITxtRecord.cs \
	Mono.Zeroconf/RegisterService.cs \
	Mono.Zeroconf/RegisterServiceEventArgs.cs \
	Mono.Zeroconf/RegisterServiceEventHandler.cs \
	Mono.Zeroconf/ServiceBrowseEventArgs.cs \
	Mono.Zeroconf/ServiceBrowseEventHandler.cs \
	Mono.Zeroconf/ServiceBrowser.cs \
	Mono.Zeroconf/ServiceErrorCode.cs \
	Mono.Zeroconf/ServiceResolvedEventArgs.cs \
	Mono.Zeroconf/ServiceResolvedEventHandler.cs \
	Mono.Zeroconf/TxtRecord.cs \
	Mono.Zeroconf/TxtRecordItem.cs

SOURCES = $(MONO_ZEROCONF_SRC)

all: $(ASSEMBLY)

$(ASSEMBLY): $(SOURCES) $(POLICY_ASSEMBLIES)
	$(MCS) -debug -keyfile:$(top_srcdir)/src/mono-zeroconf.snk -target:library -out:$@ $(SOURCES)

$(ASSEMBLY).mdb: $(ASSEMBLY)

install-data-local: gac-install

uninstall-local: gac-uninstall

include $(top_srcdir)/src/Makefile.include

EXTRA_DIST = $(SOURCES) Mono.Zeroconf.csproj
CLEANFILES = *.dll *.mdb $(POLICY_ASSEMBLIES) $(POLICY_CONFIGS)
DISTCLEANFILES = *.pidb
MAINTAINERCLEANFILES = Makefile.in

