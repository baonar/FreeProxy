BASE=../../../../..

IKS_DIR=$(BASE)/libs/iksemel
IKS_LA=$(IKS_DIR)/src/libiksemel.la
LOCAL_CFLAGS += -I../ -I$(BASE)/libs/iksemel/include 
LOCAL_OBJS= $(PCRE_LA) $(IKS_LA) main.o ../iks_helpers.o
LOCAL_SOURCES= main.c 
include $(BASE)/build/modmake.rules

$(IKS_LA): $(IKS_DIR) $(IKS_DIR)/.update
	@cd $(IKS_DIR) && $(MAKE)
	@$(TOUCH_TARGET)

local_all:
	libtool --mode=link gcc main.o ../iks_helpers.o -o test test_iks.la

local_clean:
	-rm test
