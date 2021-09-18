******** openmvg installation:********

git clone --recursive https://github.com/openMVG/openMVG.git

cd openMVG_Build/

cmake -DCMAKE_BUILD_TYPE=RELEASE ../openMVG/src/

sudo cmake --build . --target install


2. 

usage:

openMVG_main_SfMInit_ImageListing -i ./SceauxCastle -f 1536 -o ./SceauxCastle

openMVG_main_ComputeFeatures -i ./SceauxCastle/sfm_data.json -o ./SceauxCastle

openMVG_main_ComputeMatches -i ./SceauxCastle/sfm_data.json -o ./SceauxCastle

openMVG_main_IncrementalSfM -i ./SceauxCastle/sfm_data.json -m ./SceauxCastle/ -o ./SceauxCastle/reconstruction

openMVG_main_ComputeSfM_DataColor -i ./SceauxCastle/reconstruction/sfm_data.bin -o ./SceauxCastle/colored.ply

openMVG_main_ComputeStructureFromKnownPoses -i ./SceauxCastle/reconstruction/sfm_data.bin -m ./SceauxCastle/ -o ./SceauxCastle/reconstruction/robust.bin -f ./SceauxCastle/matches.f.bin


error:
double free or corruption (out)
Aborted (core dumped)

solution: open openMVG/src/CMakeLists.txt
comment row 260 (around) #find_package(Ceres QUIET HINTS ${CERES_DIR_HINTS})











