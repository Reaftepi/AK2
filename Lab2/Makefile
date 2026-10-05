CXX = g++
CXXFLAGS = -Wall -fPIC
LIB = libcalculator.so
TARGET = my_app

# окремо файли для бібліотеки і для програми
LIB_SOURCES = calculator.cpp
APP_SOURCES = main.cpp
LIB_OBJECTS = $(LIB_SOURCES:.cpp=.o)
APP_OBJECTS = $(APP_SOURCES:.cpp=.o)

all: $(LIB) $(TARGET)

$(LIB): $(LIB_OBJECTS)
	$(CXX) -shared -o $@ $^

$(TARGET): $(APP_OBJECTS) $(LIB)
	$(CXX) $(CXXFLAGS) -o $@ $(APP_OBJECTS) -L. -lcalculator

%.o: %.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

clean:
	rm -f $(LIB_OBJECTS) $(APP_OBJECTS) $(TARGET) $(LIB)

.PHONY: all clean
