CXX	?= g++
CXXFLAGS	= -march=native -Wall -Wextra -pedantic -std=c++11 -pthread -Wl,--no-as-needed  -I../include
CXX_RELEASE_FLAGS = -O3 -flto -DNDEBUG


binaries=spdlog-bench spdlog-bench-mt spdlog-async zf_log-bench zf_log-bench-mt boost-bench boost-bench-mt glog-bench glog-bench-mt g2log-async easylogging-bench easylogging-bench-mt

all: $(binaries)

spdlog-bench: spdlog-bench.cpp
	$(CXX) spdlog-bench.cpp -o spdlog-bench $(CXXFLAGS) $(CXX_RELEASE_FLAGS)
	
spdlog-bench-mt: spdlog-bench-mt.cpp
	$(CXX) spdlog-bench-mt.cpp -o spdlog-bench-mt  $(CXXFLAGS) $(CXX_RELEASE_FLAGS)
	
spdlog-async: spdlog-async.cpp
	$(CXX) spdlog-async.cpp -o spdlog-async  $(CXXFLAGS) $(CXX_RELEASE_FLAGS)


ZF_LOG_FLAGS = -I../../zf_log.git/zf_log/
zf_log-bench: zf_log-bench.cpp
	$(CXX) zf_log-bench.cpp -o zf_log-bench  $(CXXFLAGS) $(CXX_RELEASE_FLAGS) $(ZF_LOG_FLAGS)

zf_log-bench-mt: zf_log-bench-mt.cpp
	$(CXX) zf_log-bench-mt.cpp -o zf_log-bench-mt  $(CXXFLAGS) $(CXX_RELEASE_FLAGS) $(ZF_LOG_FLAGS)
	

BOOST_FLAGS	= -DBOOST_LOG_DYN_LINK  -I/usr/include -lboost_log  -lboost_log_setup -lboost_filesystem -lboost_system -lboost_thread -lboost_regex -lboost_date_time -lboost_chrono

boost-bench: boost-bench.cpp
	$(CXX) boost-bench.cpp -o boost-bench $(CXXFLAGS) $(BOOST_FLAGS) $(CXX_RELEASE_FLAGS)
	
boost-bench-mt: boost-bench-mt.cpp
	$(CXX) boost-bench-mt.cpp -o boost-bench-mt $(CXXFLAGS) $(BOOST_FLAGS) $(CXX_RELEASE_FLAGS)	


GLOG_FLAGS = -lglog
glog-bench: glog-bench.cpp
	$(CXX) glog-bench.cpp -o glog-bench $(CXXFLAGS) $(GLOG_FLAGS) $(CXX_RELEASE_FLAGS)
	
glog-bench-mt: glog-bench-mt.cpp
	$(CXX) glog-bench-mt.cpp -o glog-bench-mt $(CXXFLAGS) $(GLOG_FLAGS) $(CXX_RELEASE_FLAGS)	


G2LOG_FLAGS = -I/home/gabi/devel/g2log/g2log/src -L/home/gabi/devel/g2log/g2log -llib_g2logger 
g2log-async: g2log-async.cpp
	$(CXX) g2log-async.cpp -o g2log-async $(CXXFLAGS) $(G2LOG_FLAGS) $(CXX_RELEASE_FLAGS)
	

EASYL_FLAGS = -I../../easylogging/src/
easylogging-bench: easylogging-bench.cpp
	$(CXX) easylogging-bench.cpp -o easylogging-bench $(CXXFLAGS) $(EASYL_FLAGS) $(CXX_RELEASE_FLAGS)
easylogging-bench-mt: easylogging-bench-mt.cpp
	$(CXX) easylogging-bench-mt.cpp -o easylogging-bench-mt $(CXXFLAGS) $(EASYL_FLAGS) $(CXX_RELEASE_FLAGS)	
	
.PHONY: clean

clean:
	rm -f *.o logs/* $(binaries)


rebuild: clean all



