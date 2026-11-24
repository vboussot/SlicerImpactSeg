cmake_minimum_required(VERSION 3.5)

project(ImpactSeg)

#-----------------------------------------------------------------------------
# Extension meta-information
set(EXTENSION_HOMEPAGE "https://github.com/vboussot/SlicerImpactSeg")
set(EXTENSION_CATEGORY "Segmentation")
set(EXTENSION_CONTRIBUTORS "Valentin Boussot (University of Rennes, France), Cédric Hémon (University of Rennes, France), Jean-Louis Dillenseger (University of Rennes, France)")
set(EXTENSION_DESCRIPTION "Deep learning-based anatomical segmentation and quality assurance tools powered by KonfAI segmentation models (ImpactSeg, MRSegmentator, TotalSegmentator).")
set(EXTENSION_ICONURL "https://raw.githubusercontent.com/vboussot/SlicerImpactSeg/main/ImpactSeg.png")
set(EXTENSION_SCREENSHOTURLS "https://raw.githubusercontent.com/vboussot/SlicerImpactSeg/main/Screenshots/main.png https://raw.githubusercontent.com/vboussot/SlicerImpactSeg/main/Screenshots/tutorial/04-coarse.jpg https://raw.githubusercontent.com/vboussot/SlicerImpactSeg/main/Screenshots/tutorial/05-evaluation.jpg https://raw.githubusercontent.com/vboussot/SlicerImpactSeg/main/Screenshots/tutorial/06-uncertainty.jpg")
set(EXTENSION_DEPENDS "KonfAI")

#-----------------------------------------------------------------------------
# Extension dependencies
find_package(Slicer REQUIRED)
include(${Slicer_USE_FILE})

#-----------------------------------------------------------------------------
# Extension modules
add_subdirectory(ImpactSeg)
## NEXT_MODULE

#-----------------------------------------------------------------------------
include(${Slicer_EXTENSION_GENERATE_CONFIG})
include(${Slicer_EXTENSION_CPACK})
