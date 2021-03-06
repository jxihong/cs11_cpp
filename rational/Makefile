PROG := rational
CXX := g++

COMPILER_OPTIONS := -m64 -Wall -Wextra -Wshadow -Werror -pedantic -Iinclude
CXXFLAGS := -std=c++11 -Weffc++ $(COMPILER_OPTIONS)
LDFLAGS := -Wlv--no-as-needed -lm

DEBUGFLAGS := -g -O0 -D _DEBUG
RELEASEFLAGS := -O2 -D NDEBUG

TARGET  := rational-test
SOURCES := $(shell echo src/*.cpp)
HEADERS := $(shell echo include/*.h)
COMMON  :=
OBJECTS := $(SOURCES:.cpp=.o)

all: $(TARGET)

$(TARGET): $(OBJECTS) $(COMMON)
	$(CXX) $(FLAGS) $(CXXFLAGS) $(DEBUGFLAGS) -o $(TARGET) $(OBJECTS)

release: $(SOURCES) $(HEADERS) $(COMMON)
	$(CXX) $(FLAGS) $(CXXFLAGS) $(RELEASEFLAGS) -o $(TARGET) $(SOURCES)

zip:
	-zip $(PROG).zip $(HEADERS) $(SOURCES) Makefile

clean:
	-rm -f $(TARGET) $(OBJECTS) $(PROG).zip

%.o: %.cpp $(HEADERS) $(COMMON)
	$(CXX) $(CXXFLAGS) $(DEBUGFLAGS) -c -o $@ $<

.PHONY : all release
