ifeq ($(TESTSROOTDIR),)
  include ../testcase.mk
else
  include $(TESTSROOTDIR)/testcase.mk
endif
export TEST_TIMEOUT=50m


CFLAGS+=-I$(SRCHOME)/cdb2api -I$(SRCHOME)/bbinc

CDB2LIBS=$(SYSPATH) $(SRCHOME)/cdb2api/libcdb2api.a -lprotobuf-c -lpthread -lssl -lcrypto -L$(SRCHOME)/bb -lbb



tool: 
	make client

client: client.o
	$(CC) -g -o $@ $< $(CDB2LIBS) 

%.o: %.c
	echo $(CC) -o $@ -c $< $(CFLAGS) 
	$(CC) -g -o $@ -c $< $(CFLAGS) 
