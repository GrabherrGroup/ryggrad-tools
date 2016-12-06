cmake_minimum_required(VERSION 3.3)
project(ryggrad-base)

# include directory in find path where all dependency modules exist
include_directories(./)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread -std=c++14 -O3 -w")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_HOME_DIRECTORY}/bin)


set(SOURCE_FILES_TRANSCRIPTOMEFROMVARYK   ryggrad/src/base/FileParser.cc ryggrad/src/general/DNAVector.cc ryggrad/src/base/StringUtil.cc ryggrad/src/aligns/KmerAlignCore.cc ryggrad/src/util/mutil.cc src/kmers/KmerTable.cc src/kmers/NonRedKmerTable.cc src/kmers/TranscriptomeFromVaryK.cc) 

set(SOURCE_FILES_FINDORFS  ryggrad/src/base/FileParser.cc ryggrad/src/general/DNAVector.cc ryggrad/src/base/StringUtil.cc ryggrad/src/util/mutil.cc src/sequence/FindORFs.cc) 

set(SOURCE_FILES_NUCTOPROT  ryggrad/src/base/FileParser.cc ryggrad/src/general/DNAVector.cc ryggrad/src/base/StringUtil.cc ryggrad/src/util/mutil.cc src/sequence/NucToProt.cc) 

set(SOURCE_FILES_SPLITFASTA  ryggrad/src/base/FileParser.cc ryggrad/src/general/DNAVector.cc ryggrad/src/base/StringUtil.cc ryggrad/src/util/mutil.cc src/sequence/SplitFasta.cc) 

set(SOURCE_FILES_FASTABYLENGTH  ryggrad/src/base/FileParser.cc ryggrad/src/general/DNAVector.cc ryggrad/src/base/StringUtil.cc ryggrad/src/util/mutil.cc src/sequence/FastaByLength.cc) 

add_executable(TranscriptomeFromVaryK ${SOURCE_FILES_TRANSCRIPTOMEFROMVARYK})
add_executable(FindORFs ${SOURCE_FILES_FINDORFS})
add_executable(NucToProt ${SOURCE_FILES_NUCTOPROT})
add_executable(SplitFasta ${SOURCE_FILES_SPLITFASTA})
add_executable(FastaByLength ${SOURCE_FILES_FASTABYLENGTH})


# ryggrad-tools binaries
#set(SOURCE_FILES_TESTCOMPILE src/base/ErrorHandling.cc src/base/FileParser.cc src/base/StringUtil.cc test/TestCompile.cc src/util/mutil.cc src/visual/Eps.cc) 

#add_executable(TestCompile ${SOURCE_FILES_TESTCOMPILE})




