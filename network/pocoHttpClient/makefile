#This is cross platform make file. 
# To build on arm platform, please run "source env.sh" first.

CLIENT = httpClient

CLIENT_SRC = main.cpp

INC = -I/usr/local/include -I$(SYSTEM_ROOT)/usr/include -I$(SYSTEM_ROOT)/usr/include/base -I.

LB_INC = -L/usr/local/lib -L$(SYSTEM_ROOT)/usr/lib  -lPocoNetd -lPocoFoundationd -lPocoNetSSLd -lcrypto -lssl -lPocoUtild


CFLAGS +=  $(INC) -Wall -Werror
CXXFLAGS += $(CFLAGS) -std=c++11 -g
LDFLAGS +=  $(LB_INC) \
            -Wl,-rpath-link,/usr/local/lib \
            -Wl,-rpath-link,$(SYSTEM_ROOT)/usr/lib \
            -Wl,-rpath-link,$(SYSTEM_ROOT)/lib 

CLIENT_OBJ = $(patsubst %.cpp,%.o,$(CLIENT_SRC))
#COBJS = $(patsubst %.c,%.o,$(CSRC))

all :$(CLIENT)
	
$(CLIENT) : $(CLIENT_OBJ)
	$(CXX) $^ $(LDFLAGS)  -o $@ 


#.PHONY: clean
clean:
	rm -rf $(CLIENT)
	rm -rf $(CLIENT_OBJ)