message(STATUS "SplineDrivenImageSlicer: Building as a Remote VTK module")

if(VTK_VERSION VERSION_LESS "8.90.0")
  set(sources
    vtkFrenetSerretFrame.cxx
    vtkSplineDrivenImageSlicer.cxx  
  )

  vtk_module_library(SplineDrivenImageSlicer ${sources})
else()
  set(classes
    vtkSplineDrivenImageSlicer
    vtkFrenetSerretFrame
  )

  vtk_module_add_module(VTK::SplineDrivenImageSlicer
    CLASSES ${classes}
  )
endif()
