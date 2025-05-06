CXX = g++
CXXFLAGS = -std=c++17 -march=native -O3 -fopenmp
LDFLAGS = -lgmp
TARGET = search_opt
SRC = search_opt.cpp

# CPU affinity configuration
# Set the CPU cores to use (e.g., 0-3 for cores 0,1,2,3)
CPU_CORES ?= 0-112
TASKSET = taskset -c $(CPU_CORES)

all: $(TARGET)

$(TARGET): $(SRC)
	$(CXX) $(CXXFLAGS) $< $(LDFLAGS) -o $@

clean:
	rm -f $(TARGET)
	rm -f output/search_results_task*.txt

# Task targets
output/search_results_task1.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 1

output/search_results_task2.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 2

output/search_results_task3.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 3

output/search_results_task4.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 4

output/search_results_task5.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 5

output/search_results_task6.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 6

output/search_results_task71.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 7-1

output/search_results_task72.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 7-2

output/search_results_task73.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 7-3

output/search_results_task74.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 7-4

output/search_results_task81.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 8-1

output/search_results_task82.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 8-2

output/search_results_task83.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 8-3

output/search_results_task84.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 8-4

output/search_results_task85.txt: $(TARGET)
	$(TASKSET) ./$(TARGET) 8-5

# Run all tasks
all-tasks: output/search_results_task1.txt output/search_results_task2.txt output/search_results_task3.txt output/search_results_task4.txt output/search_results_task5.txt output/search_results_task6.txt output/search_results_task71.txt output/search_results_task72.txt output/search_results_task73.txt output/search_results_task74.txt output/search_results_task81.txt output/search_results_task82.txt output/search_results_task83.txt output/search_results_task84.txt output/search_results_task85.txt

.PHONY: all clean all-tasks
