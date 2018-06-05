---?image=assets/images/gitpitch-audience.jpg
@title[EDK_II_Porting_Projects_pres]
<br><br><br><br><br>
## <span class="gold"   >UEFI & EDK II Training</span>

#### Porting an Existing Project 

<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>
Note:
  PITCHME.md for UEFI / EDK II Training  Porting an Existing Project with EDK II

  Copyright (c) 2018, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.



---  
@title[Lesson Objective]
<BR>
### <p align="center"<span class="gold"   >Lesson Objective </span></p><br>

<!---  Add bullets using https://fontawesome.com/cheatsheet certificate
-->
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;Define the porting task list for porting existing<br>&nbsp;&nbsp;&nbsp;&nbsp; platforms in EDK II in order to boot to the UEFI Shell</span> </li>
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Explain the EDK II infrastructure, porting libraries,<br>&nbsp;&nbsp;&nbsp;&nbsp; library classes, PCDs, and directory structures</span></li>
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Determine the necessary porting for each phase<br> &nbsp;&nbsp&nbsp;&nbsp;of a new EDK II platform Project</span> </li>
</ul>

---?image=assets/images/binary-strings-black2.jpg
@title[EDK II Infrastructure Section]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EDK II Infrastructure </span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Review of EDK II</span>


---?image=/assets/images/slides/Slide4.JPG
<!-- .slide: data-transition="none" -->
@title[EDK II Infrastructure]
<p align="right"><span class="gold" >EDK II Infrastructure</span></p>


Note:

- First off we have the infrastructure.
- So the infrastructure is what are the new things added for EDK II?

- First, the directory structure, the directory structure for EDK II is now structured so that all of the platform package contents are in subdirectories under the platform package. So we will have a new platform package, and in that directory there will be subdirectories where we will have all of the reported modules and code for our new platform. Anything we update will be in this directory package. So what we will see is our build description files.

- The other thing that is different is the libraries. We see with EDK II we have a library class and library instances. If we take our existing platform and look at the library instances we may have to update those for our new platform package.

- The third thing that is different is the new platform configuration database or PCD. What we will see with this is to port our new platform we may only be changing a PCD value and we may not even change the source code.

- Directory Structure
  - The package for the platform contains subdirectories for ported modules
  - Text files: FDF, DSC, DEC

- Libraries – Library class and library instances may need to be ported for the platform

- PCD – PCD helps with porting, and may mean not changing any of the source code


+++?image=/assets/images/slides/Slide5.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[EDK II Infrastructure 02]
<p align="right"><span class="gold" >EDK II Infrastructure</span></p>


Note:

- First off we have the infrastructure.
- So the infrastructure is what are the new things added for EDK II?

- First, the directory structure, the directory structure for EDK II is now structured so that all of the platform package contents are in subdirectories under the platform package. So we will have a new platform package, and in that directory there will be subdirectories where we will have all of the reported modules and code for our new platform. Anything we update will be in this directory package. So what we will see is our build description files.

- The other thing that is different is the libraries. We see with EDK II we have a library class and library instances. If we take our existing platform and look at the library instances we may have to update those for our new platform package.

- The third thing that is different is the new platform configuration database or PCD. What we will see with this is to port our new platform we may only be changing a PCD value and we may not even change the source code.

- Directory Structure
  - The package for the platform contains subdirectories for ported modules
  - Text files: FDF, DSC, DEC

- Libraries – Library class and library instances may need to be ported for the platform

- PCD – PCD helps with porting, and may mean not changing any of the source code



+++?image=/assets/images/slides/Slide6.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[EDK II Infrastructure 03]
<p align="right"><span class="gold" >EDK II Infrastructure</span></p>


Note:

- First off we have the infrastructure.
- So the infrastructure is what are the new things added for EDK II?

- First, the directory structure, the directory structure for EDK II is now structured so that all of the platform package contents are in subdirectories under the platform package. So we will have a new platform package, and in that directory there will be subdirectories where we will have all of the reported modules and code for our new platform. Anything we update will be in this directory package. So what we will see is our build description files.

- The other thing that is different is the libraries. We see with EDK II we have a library class and library instances. If we take our existing platform and look at the library instances we may have to update those for our new platform package.

- The third thing that is different is the new platform configuration database or PCD. What we will see with this is to port our new platform we may only be changing a PCD value and we may not even change the source code.

- Directory Structure
  - The package for the platform contains subdirectories for ported modules
  - Text files: FDF, DSC, DEC

- Libraries – Library class and library instances may need to be ported for the platform

- PCD – PCD helps with porting, and may mean not changing any of the source code



+++?image=/assets/images/slides/Slide7.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[EDK II Infrastructure 04]
<p align="right"><span class="gold" >EDK II Infrastructure</span></p>


Note:

- First off we have the infrastructure.
- So the infrastructure is what are the new things added for EDK II?

- First, the directory structure, the directory structure for EDK II is now structured so that all of the platform package contents are in subdirectories under the platform package. So we will have a new platform package, and in that directory there will be subdirectories where we will have all of the reported modules and code for our new platform. Anything we update will be in this directory package. So what we will see is our build description files.

- The other thing that is different is the libraries. We see with EDK II we have a library class and library instances. If we take our existing platform and look at the library instances we may have to update those for our new platform package.

- The third thing that is different is the new platform configuration database or PCD. What we will see with this is to port our new platform we may only be changing a PCD value and we may not even change the source code.

- Directory Structure
  - The package for the platform contains subdirectories for ported modules
  - Text files: FDF, DSC, DEC

- Libraries – Library class and library instances may need to be ported for the platform

- PCD – PCD helps with porting, and may mean not changing any of the source code


---?image=/assets/images/slides/Slide9.JPG
<!-- .slide: data-transition="none" -->
@title[EDK II Infrastructure Review]
<p align="right"><span class="gold" >EDK II Infrastructure - review</span></p>


Note:


+++?image=/assets/images/slides/Slide10.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[EDK II Infrastructure Review 02]
<p align="right"><span class="gold" >EDK II Infrastructure - review</span></p>


Note:



+++?image=/assets/images/slides/Slide11.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[EDK II Infrastructure Review 03]
<p align="right"><span class="gold" >EDK II Infrastructure - review</span></p>


Note:


---?image=/assets/images/slides/Slide13.JPG
<!-- .slide: data-transition="none" -->
@title[New Package Directory]
<p align="right"><span class="gold" >New Package Directory</span></p>


Note:



+++?image=/assets/images/slides/Slide14.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[New Package Directory 02]
<p align="right"><span class="gold" >New Package Directory</span></p>


Note:



+++?image=/assets/images/slides/Slide15.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[New Package Directory 03]
<p align="right"><span class="gold" >New Package Directory</span></p>


Note:



---?image=/assets/images/slides/Slide17.JPG
@title[Libraries]
<p align="center"><span class="gold" ><b>Libraries</b></span></p>


Note:

- DSC maps library-class to library-instances
- Global, by type, individual override based on desired implimentation
- Effected by size, speed, built in, binary distribution 
- PCI example
  - PciCfg – Protocol function call by GUID (PEI)
  - PciRootBridgeIo – Protocol function call by GUID (DXE)
  - Syntax in DSC file
  - 	[libraryclasses] 
  - 	LibraryClassName|Path/To/LibInstanceNameInstance1.inf
  
  
- another Note; Workspace relative paths!
  -  Check for existing library instances.
  - Search INF for string: LIBRARY_CLASS  =



---?image=/assets/images/slides/Slide19.JPG
@title[Library Classes in DSC ]
<p align="right"><span class="gold" >Library Classes Section in DSC</span></p>


Note:

Example - 

<pre>
 DebugLib class in NewProjectPkg.dsc

 [LibraryClasses]
     DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf
     • • •
 [LibraryClasses.common.DXE_CORE]
         • • •
    DebugLib|IntelFrameworkModulePkg/Library/PeiDxeDebugLibReportStatusCode/
           PeiDxeDebugLibReportStatusCode.inf  
        • • •
 [LibraryClasses.common.DXE_SMM_DRIVER]
    DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf

 [Components]
      • • •
 MyPath/MyModule.inf {
  <LibraryClasses>
    DebugLib|MdePkg/Library/BaseDebugLibSerialPort.inf
 }
</pre>


---?image=/assets/images/slides/Slide21.JPG
@title[PCD Types]
<p align="right"><span class="gold" >PCD Types</span></p>


Note:

- FeatureFlag 
  - Replaces a switch MACRO to enable/disable a feature (TRUE or FALSE)
- FixedAtBuild
  - Replaces a macro that produced a customizable value
  - Value of this PCD type is determined at build time and is stored in the code section of a module’s PE image 
- PatchableInModule
  - Value is stored in the data section, rather than the code section, of the module’s PE image. 
- Dynamic / DyanmicEx / DynamicHii / DynamicVpd
  - Value is assigned by one module and is accessed by other modules in execution time 
- Syntax Examples
	- [pcdsFeatureFlag.common] [pcdsFixedAtBuild.IA32] [pcdsFixedAtBuild.X64]   [pcdsFixedAtBuild.IPF] [pcdsFixedAtBuild.EBC]   [pcdsDynamic.IA32] [pcdsDynamicEx.X64] 

	


---?image=/assets/images/slides/Slide23.JPG
<!-- .slide: data-transition="none" -->
@title[PCD Syntax]
<p align="right"><span class="gold" >PCD Syntax</span></p>


Note:

- Use slide in another lesson for the template and then build the red and green text


- PCD defined in the DEC file from any package
- [Guids.common]
   - PcdTokenSpaceGuidName={ 0x914AEBE7, 0x4635, 0x459b, { 0xAA, . . .}}

- [Pcds...]
  - PcdTokenSpaceGuidName.PcdTokenName|Value[|DatumType[|MaxSize]]|Token
  - PCD usage listed in INF file for module
- […Pcd…] 
  - PcdTokenSpaceGuidName.PcdTokenName|[Value]
  - Value of PCD set in NewPlatform.dsc
- [Pcds...]
  - PcdTokenSpaceGuidName.PcdTokenName|Value[|DatumType[|MaximumDatumSize]]
- Example used in NewProject.dsc
- [PcdsFixedAtBuild.IA32]
  -  gEfiIchTokenSpaceGuid.PcdIchAcpiIoPortBaseAddress|0x400
  -  gNewProjectTokenSpaceGuid.PcdFlashAreaBaseAddress|0xFFF00000
  - gNewProjectTokenSpaceGuid.PcdFlashAreaSize|0x100000
 

+++?image=/assets/images/slides/Slide24.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PCD Syntax 02]
<p align="right"><span class="gold" >PCD Syntax</span></p>


Note:

- Use slide in another lesson for the template and then build the red and green text


- PCD defined in the DEC file from any package
- [Guids.common]
   - PcdTokenSpaceGuidName={ 0x914AEBE7, 0x4635, 0x459b, { 0xAA, . . .}}

- [Pcds...]
  - PcdTokenSpaceGuidName.PcdTokenName|Value[|DatumType[|MaxSize]]|Token
  - PCD usage listed in INF file for module
- […Pcd…] 
  - PcdTokenSpaceGuidName.PcdTokenName|[Value]
  - Value of PCD set in NewPlatform.dsc
- [Pcds...]
  - PcdTokenSpaceGuidName.PcdTokenName|Value[|DatumType[|MaximumDatumSize]]
- Example used in NewProject.dsc
- [PcdsFixedAtBuild.IA32]
  -  gEfiIchTokenSpaceGuid.PcdIchAcpiIoPortBaseAddress|0x400
  -  gNewProjectTokenSpaceGuid.PcdFlashAreaBaseAddress|0xFFF00000
  - gNewProjectTokenSpaceGuid.PcdFlashAreaSize|0x100000
 

---?image=assets/images/binary-strings-black2.jpg
@title[Porting Task List Section]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Porting Task List</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;What is the best approach for how to port?</span>


---?image=/assets/images/slides/Slide27_1.JPG
@title[Porting Approach]
### <p align="center"><font color="black"<b>Approach – Porting EDK II</b></font></p>
<br>
@ul[no-bullet]
- <p align="right"><span style="font-size:01.1em" ><span style="background-color: #fdb819">&nbsp;&nbsp;&nbsp; <b>Search Work Space&nbsp;</b>&nbsp;&nbsp;</span></span></p><br><br><br>
- <p align="left"><span style="font-size:01.1em" ><span style="background-color: #92d050">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <b>Find Similar EDK II Projects</b>&nbsp;&nbsp;&nbsp;</span></span></p>
- <p align="center"><span style="font-size:01.1em" ><span style="background-color: #7030a0">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <b>Boot to UEFI Shell&nbsp;</b>&nbsp;&nbsp;</span></span></p>
@ulend


Note:

- Many examples of packages in the UDK / EDK II source base 
- Find a similar package or platform or project that meets target project needs
-  Build description files are text files using basic text editor to update – no GUI 




---?image=/assets/images/slides/Slide32.JPG
<!-- .slide: data-transition="none" -->
@title[Porting Task List Section]
<p align="center"><span class="gold" ><b>Porting Task List</b></span></p>




+++?image=/assets/images/slides/Slide33.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Task List 02]
<p align="center"><span class="gold" ><b>Porting Task List</b></span></p>

Note:


+++?image=/assets/images/slides/Slide34.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Task List 03]
<p align="center"><span class="gold" ><b>Porting Task List</b></span></p>

Note:


+++?image=/assets/images/slides/Slide35.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Task List 04]
<p align="center"><span class="gold" ><b>Porting Task List</b></span></p>

Note:


+++?image=/assets/images/slides/Slide36.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Task List 05]
<p align="center"><span class="gold" ><b>Porting Task List</b></span></p>

Note:


+++?image=/assets/images/slides/Slide37.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Task List 06]
<p align="center"><span class="gold" ><b>Porting Task List</b></span></p>

Note:


---?image=/assets/images/slides/Slide39.JPG
@title[New Directory Structure  ]
<p align="right"><span class="gold" >New Directory Structure  </span></p>

Note:


---?image=/assets/images/slides/Slide41_1.JPG
<!-- .slide: data-transition="none" -->
@title[Creating a New Project Directory]
<p align="right"><span class="gold" >New Directory Structure  </span></p>

Note:
-  The platform package directory contains project files
-  DEC
-  DSC
-  FDF
-  Specific platform directories have files for other functions
-  PEI
-  DXE
-  SMM
-  SIO
-  Setup
-  Library
-  Etc…



+++?image=/assets/images/slides/Slide41_2.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Creating a New Project Directory 02]
<p align="right"><span class="gold" >New Directory Structure  </span></p>

Note:
-  The platform package directory contains project files
-  DEC
-  DSC
-  FDF
-  Specific platform directories have files for other functions
-  PEI
-  DXE
-  SMM
-  SIO
-  Setup
-  Library
-  Etc…


+++?image=/assets/images/slides/Slide41_3.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Creating a New Project Directory 03]
<p align="right"><span class="gold" >New Directory Structure  </span></p>

Note:
-  The platform package directory contains project files
-  DEC
-  DSC
-  FDF
-  Specific platform directories have files for other functions
-  PEI
-  DXE
-  SMM
-  SIO
-  Setup
-  Library
-  Etc…


+++?image=/assets/images/slides/Slide41_4.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Creating a New Project Directory 04]
<p align="right"><span class="gold" >New Directory Structure  </span></p>

Note:
-  The platform package directory contains project files
-  DEC
-  DSC
-  FDF
-  Specific platform directories have files for other functions
-  PEI
-  DXE
-  SMM
-  SIO
-  Setup
-  Library
-  Etc…


---?image=/assets/images/slides/Slide42.JPG
<!-- .slide: data-transition="none" -->
@title[PCD Example with New Project ]
<p align="right"><span class="gold" >PCD Example with New Project   </span></p>

Note:

-  PCDs are declared in corresponding Silicon and Chipset Packages, according to how they are used with default values in the package DEC files.

-  PCDs are assigned values in the Project Package DSC file, overriding values in the DEC file.


+++?image=/assets/images/slides/Slide43.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PCD Example with New Project 02]
<p align="right"><span class="gold" >PCD Example with New Project   </span></p>

Note:

-  PCDs are declared in corresponding Silicon and Chipset Packages, according to how they are used with default values in the package DEC files.

-  PCDs are assigned values in the Project Package DSC file, overriding values in the DEC file.



---?image=/assets/images/slides/Slide45.JPG
<!-- .slide: data-transition="none" -->
@title[Porting Task List Section 04]
<p align="center"><span class="gold" ><b>Porting Task List</b></span></p>




+++?image=/assets/images/slides/Slide46.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Task List Section 04 - 2]
<p align="center"><span class="gold" ><b>Porting Task List</b></span></p>

Note:

This will be the longest task and depending on the project may take several weeks




---?image=/assets/images/slides/Slide48.JPG
<!-- .slide: data-transition="none" -->
@title[Platform Initialization: SEC Phase]
<p align="right"><span class="gold" >Platform Initialization: SEC Phase</span></p>

Note:
-  Minimal code
-  Execute in place (XIP) from flash
-  Execution started by reset vector
-  Enables temp memory for C code (data & stack)
-  Transfers control to PEI


-  Let’s start with the SEC phase.
-  What do we need to be current sermon about in the SEC?
-  We will have Minimal code and we are most likely in assembly language for the particular processor architecture.
-  We will be executing from flash , so this means the code will not be compressed.
-  A point to take especially if you are going to be using a hardware debugger, is we will start Execution at the reset vector
-  It’s job is to Enables temp memory
-  Set up the Data and Stack Cached areas . This sets up our cache as RAM or our cache as no eviction mode.
-  Which will Enable the C Code
-  And then it will finally Transfer control to PEI

-  What we are showing at the right of the slide is the exact location in the EDK II source tree of the reset vector. For X86 Intel architecture all the code will be in the directory Ia32FamilyCpuPkg and the reset vector will be in the file ResetVec.asm16. for this particular file to reset Vector will start to execute the code in this file. There are approximately about three assembly language instructions before it will make a jump into a platform’s ported SEC library source code. This is where we would need to start to port our new platform code.
-  The Middle example is for Itanium and would be similar to the X86 example. In this example there is the SALE_ENTRY.
-  Currently we only have two processor architectures but if we had a third the “OtherArch” example would be where it would be located.




+++?image=/assets/images/slides/Slide49.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Platform Initialization: SEC Phase 02]
<p align="right"><span class="gold" >Platform Initialization: SEC Phase</span></p>


Note:
-  Minimal code
-  Execute in place (XIP) from flash
-  Execution started by reset vector
-  Enables temp memory for C code (data & stack)
-  Transfers control to PEI


-  Let’s start with the SEC phase.
-  What do we need to be current sermon about in the SEC?
-  We will have Minimal code and we are most likely in assembly language for the particular processor architecture.
-  We will be executing from flash , so this means the code will not be compressed.
-  A point to take especially if you are going to be using a hardware debugger, is we will start Execution at the reset vector
-  It’s job is to Enables temp memory
-  Set up the Data and Stack Cached areas . This sets up our cache as RAM or our cache as no eviction mode.
-  Which will Enable the C Code
-  And then it will finally Transfer control to PEI

-  What we are showing at the right of the slide is the exact location in the EDK II source tree of the reset vector. For X86 Intel architecture all the code will be in the directory Ia32FamilyCpuPkg and the reset vector will be in the file ResetVec.asm16. for this particular file to reset Vector will start to execute the code in this file. There are approximately about three assembly language instructions before it will make a jump into a platform’s ported SEC library source code. This is where we would need to start to port our new platform code.
-  The Middle example is for Itanium and would be similar to the X86 example. In this example there is the SALE_ENTRY.
-  Currently we only have two processor architectures but if we had a third the “OtherArch” example would be where it would be located.



+++?image=/assets/images/slides/Slide50.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Platform Initialization: SEC Phase 03]
<p align="right"><span class="gold" >Platform Initialization: SEC Phase</span></p>


Note:
-  Minimal code
-  Execute in place (XIP) from flash
-  Execution started by reset vector
-  Enables temp memory for C code (data & stack)
-  Transfers control to PEI


-  Let’s start with the SEC phase.
-  What do we need to be current sermon about in the SEC?
-  We will have Minimal code and we are most likely in assembly language for the particular processor architecture.
-  We will be executing from flash , so this means the code will not be compressed.
-  A point to take especially if you are going to be using a hardware debugger, is we will start Execution at the reset vector
-  It’s job is to Enables temp memory
-  Set up the Data and Stack Cached areas . This sets up our cache as RAM or our cache as no eviction mode.
-  Which will Enable the C Code
-  And then it will finally Transfer control to PEI

-  What we are showing at the right of the slide is the exact location in the EDK II source tree of the reset vector. For X86 Intel architecture all the code will be in the directory Ia32FamilyCpuPkg and the reset vector will be in the file ResetVec.asm16. for this particular file to reset Vector will start to execute the code in this file. There are approximately about three assembly language instructions before it will make a jump into a platform’s ported SEC library source code. This is where we would need to start to port our new platform code.
-  The Middle example is for Itanium and would be similar to the X86 example. In this example there is the SALE_ENTRY.
-  Currently we only have two processor architectures but if we had a third the “OtherArch” example would be where it would be located.


---?image=/assets/images/slides/Slide52.JPG
@title[SEC Code Start]
<p align="right"><span class="gold" >SEC Code Start</span></p>


Note:

<pre>
/**
  This routine is invoked by main entry of PeiMain module during transition
  from SEC to PEI. After switching stack in the PEI core, it will restart
  with the old core data.

  @param SecCoreData     Points to a data structure containing information about the PEI core's operating
                         environment, such as the size and location of temporary RAM, the stack location and
                         the BFV location.
  @param PpiList         Points to a list of one or more PPI descriptors to be installed initially by the PEI core.
                         An empty PPI list consists of a single descriptor with the end-tag
                         EFI_PEI_PPI_DESCRIPTOR_TERMINATE_LIST. As part of its initialization
                         phase, the PEI Foundation will add these SEC-hosted PPIs to its PPI database such
                         that both the PEI Foundation and any modules can leverage the associated service
                         calls and/or code in these early PPIs
  @param Data            Pointer to old core data that is used to initialize the
                         core's data areas.
                         If NULL, it is first PeiCore entering.
						 
</pre>


---?image=/assets/images/slides/Slide54.JPG
@title[Platform SEC Lib for MinnowBoard MAX]
<p align="right"><span class="gold" >Platform SEC Lib for MinnowBoard MAX</span></p>


Note:

-  Entry point after reset vector is platform specific
  -  SecEntry.asm
  -  ModuleEntryPoint
-  SecNewProject.asm calls entry for setting up temporary memory and APs
  -  SecPlatformInitTram
  -  SecPlatformApEntryPoint
-  SecCPU.Asm sets cache for no eviction mode
  -  CPU & MTRR register defines
  -  Ia32.inc
-  NewProjectSecLib.c SEC platform main (i.e. enable FWH decode)

-  Of this slide we have what we need to port our new package platform for the SEC  phase.
-  We find this code in our new platform package directory under the library directory under the directory called something like new platform SEC lib. Under this directory we see that we have a “C”, “H” and Inf files, And we also see another directory, in our case for our example platform, we have an IA32 directory. This directory would have assembly language source files for our port.

-  Let’s take a look at the details of these files:
  -  After the reset vector and after those initial architecture specific instructions, a jump will be made into the new platform SEC library code. The Entry point after common reset vector is platform specific in SecEntry.asm  with the label ModuleEntryPoint.

-  The file SecNewProject.asm – calls the entry for setting up our temporary memory and the Application Processors
-  We will need to look at the code at the label SecPlatformInitTram where we would  make a call to set up our temporary memory. Probably the cache as RAM. But, it could be something different.
-  The label SecPlatformApEntryPoint is where we be setting up the entry point for our application processors.
-  The file SecCPU.Asm – is the actual code that Sets the Cache for no eviction mode or cache as RAM.
-  The include file  Ia32.inc – has Defines for the MTRR registers and processor specific defines  

-  Finally, the C. source code file NewProjectSecLib.c – and this file would have the Sec Platform MAIN entry– and it would be responsible for things like to Enable FWH decoding etc.





---?image=/assets/images/slides/Slide56.JPG
@title[Temporary Memory Example]
<p align="right"><span class="gold" >Temporary Memory Example</span></p>


Note:
-  This is an example!!!!!

-  SEC PCDs used to set up temp RAM size and location
  -  PcdTemporaryRamSize
  -  PcdTemporaryRamBase


---?image=/assets/images/slides/Slide58.JPG
<!-- .slide: data-transition="none" -->
@title[SEC Lib, PCD Example ]
<p align="right"><span class="gold" >SEC Lib, PCD Example </span></p>


Note:
-  SEC PCDs used to set up temp RAM size and location
  -  PcdTemporaryRamSize
  -  PcdTemporaryRamBase



+++?image=/assets/images/slides/Slide59.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[SEC Lib, PCD Example 02 ]
<p align="right"><span class="gold" >SEC Lib, PCD Example </span></p>


Note:
-  SEC PCDs used to set up temp RAM size and location
  -  PcdTemporaryRamSize
  -  PcdTemporaryRamBase


+++?image=/assets/images/slides/Slide60.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[SEC Lib, PCD Example 03 ]
<p align="right"><span class="gold" >SEC Lib, PCD Example </span></p>


Note:
-  SEC PCDs used to set up temp RAM size and location
  -  PcdTemporaryRamSize
  -  PcdTemporaryRamBase


+++?image=/assets/images/slides/Slide61.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[SEC Lib, PCD Example 04 ]
<p align="right"><span class="gold" >SEC Lib, PCD Example </span></p>


Note:
-  SEC PCDs used to set up temp RAM size and location
  -  PcdTemporaryRamSize
  -  PcdTemporaryRamBase


+++?image=/assets/images/slides/Slide62.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[SEC Lib, PCD Example 05 ]
<p align="right"><span class="gold" >SEC Lib, PCD Example </span></p>


Note:
-  SEC PCDs used to set up temp RAM size and location
  -  PcdTemporaryRamSize
  -  PcdTemporaryRamBase



---?image=/assets/images/slides/Slide64.JPG
<!-- .slide: data-transition="none" -->
@title[PEI Phase ]
<p align="right"><span class="gold" >PEI Phase </span></p>
 

Note:
-  The main platform PEI code is in a subdirectory of the platform package. (PlatformPei)
-  It references PEIMs in other packages
-  PEI code is dependant on the PEI drivers for the platform for communication to the devices


-  Determine boot mode
  -  S3 and S5 are the most common modes
  -  Recovery mode
-  Low-level initialization of the platform
  -  Find FVs that contain DXE
-  Discover and initialize main memory
-  Transfer control according to boot mode
  -  If S5 hands control to DXE
  -  If S3 uses waking vector


-  Platform PEI code can be divided into 3 phases:
  1.  Pre-Memory Initialization
    -  Initialize the memory controller
    -  Detect boot mode.
    -  Detect video adapter
  2.  Memory Initialization (MRC)
    -  Install  UEFI Memory.
    -  Capsule coalesce, Capsule Boot.
    -  Create HOB of system memory.
  3.  Post-Memory initialization
    -  PCH initialization after MRC.
    -  SIO initialization.
    - Install ResetSystem and FinvFv PPI, if  recovery boot mode.
    - Set MTRR for PEI
    - Create FV HOB and Flash HOB
    - Install RecoveryModule and AtaController PPI  if  recovery boot mode.


+++?image=/assets/images/slides/Slide65.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PEI Phase 02 ]
<p align="right"><span class="gold" >PEI Phase </span></p>
 

Note:
-  The main platform PEI code is in a subdirectory of the platform package. (PlatformPei)
-  It references PEIMs in other packages
-  PEI code is dependant on the PEI drivers for the platform for communication to the devices


-  Determine boot mode
  -  S3 and S5 are the most common modes
  -  Recovery mode
-  Low-level initialization of the platform
  -  Find FVs that contain DXE
-  Discover and initialize main memory
-  Transfer control according to boot mode
  -  If S5 hands control to DXE
  -  If S3 uses waking vector


-  Platform PEI code can be divided into 3 phases:
  1.  Pre-Memory Initialization
    -  Initialize the memory controller
    -  Detect boot mode.
    -  Detect video adapter
  2.  Memory Initialization (MRC)
    -  Install  UEFI Memory.
    -  Capsule coalesce, Capsule Boot.
    -  Create HOB of system memory.
  3.  Post-Memory initialization
    -  PCH initialization after MRC.
    -  SIO initialization.
    - Install ResetSystem and FinvFv PPI, if  recovery boot mode.
    - Set MTRR for PEI
    - Create FV HOB and Flash HOB
    - Install RecoveryModule and AtaController PPI  if  recovery boot mode.


+++?image=/assets/images/slides/Slide66.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PEI Phase 03 ]
<p align="right"><span class="gold" >PEI Phase </span></p>
 

Note:
-  The main platform PEI code is in a subdirectory of the platform package. (PlatformPei)
-  It references PEIMs in other packages
-  PEI code is dependant on the PEI drivers for the platform for communication to the devices


-  Determine boot mode
  -  S3 and S5 are the most common modes
  -  Recovery mode
-  Low-level initialization of the platform
  -  Find FVs that contain DXE
-  Discover and initialize main memory
-  Transfer control according to boot mode
  -  If S5 hands control to DXE
  -  If S3 uses waking vector


-  Platform PEI code can be divided into 3 phases:
  1.  Pre-Memory Initialization
    -  Initialize the memory controller
    -  Detect boot mode.
    -  Detect video adapter
  2.  Memory Initialization (MRC)
    -  Install  UEFI Memory.
    -  Capsule coalesce, Capsule Boot.
    -  Create HOB of system memory.
  3.  Post-Memory initialization
    -  PCH initialization after MRC.
    -  SIO initialization.
    - Install ResetSystem and FinvFv PPI, if  recovery boot mode.
    - Set MTRR for PEI
    - Create FV HOB and Flash HOB
    - Install RecoveryModule and AtaController PPI  if  recovery boot mode.


+++?image=/assets/images/slides/Slide67.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PEI Phase 04 ]
<p align="right"><span class="gold" >PEI Phase </span></p>
 

Note:
-  The main platform PEI code is in a subdirectory of the platform package. (PlatformPei)
-  It references PEIMs in other packages
-  PEI code is dependant on the PEI drivers for the platform for communication to the devices


-  Determine boot mode
  -  S3 and S5 are the most common modes
  -  Recovery mode
-  Low-level initialization of the platform
  -  Find FVs that contain DXE
-  Discover and initialize main memory
-  Transfer control according to boot mode
  -  If S5 hands control to DXE
  -  If S3 uses waking vector


-  Platform PEI code can be divided into 3 phases:
  1.  Pre-Memory Initialization
    -  Initialize the memory controller
    -  Detect boot mode.
    -  Detect video adapter
  2.  Memory Initialization (MRC)
    -  Install  UEFI Memory.
    -  Capsule coalesce, Capsule Boot.
    -  Create HOB of system memory.
  3.  Post-Memory initialization
    -  PCH initialization after MRC.
    -  SIO initialization.
    - Install ResetSystem and FinvFv PPI, if  recovery boot mode.
    - Set MTRR for PEI
    - Create FV HOB and Flash HOB
    - Install RecoveryModule and AtaController PPI  if  recovery boot mode.


+++?image=/assets/images/slides/Slide68.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PEI Phase 05 ]
<p align="right"><span class="gold" >PEI Phase </span></p>
 

Note:
-  The main platform PEI code is in a subdirectory of the platform package. (PlatformPei)
-  It references PEIMs in other packages
-  PEI code is dependant on the PEI drivers for the platform for communication to the devices


-  Determine boot mode
  -  S3 and S5 are the most common modes
  -  Recovery mode
-  Low-level initialization of the platform
  -  Find FVs that contain DXE
-  Discover and initialize main memory
-  Transfer control according to boot mode
  -  If S5 hands control to DXE
  -  If S3 uses waking vector


-  Platform PEI code can be divided into 3 phases:
  1.  Pre-Memory Initialization
    -  Initialize the memory controller
    -  Detect boot mode.
    -  Detect video adapter
  2.  Memory Initialization (MRC)
    -  Install  UEFI Memory.
    -  Capsule coalesce, Capsule Boot.
    -  Create HOB of system memory.
  3.  Post-Memory initialization
    -  PCH initialization after MRC.
    -  SIO initialization.
    - Install ResetSystem and FinvFv PPI, if  recovery boot mode.
    - Set MTRR for PEI
    - Create FV HOB and Flash HOB
    - Install RecoveryModule and AtaController PPI  if  recovery boot mode.


+++?image=/assets/images/slides/Slide69.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PEI Phase 06 ]
<p align="right"><span class="gold" >PEI Phase </span></p>
 

Note:
-  The main platform PEI code is in a subdirectory of the platform package. (PlatformPei)
-  It references PEIMs in other packages
-  PEI code is dependant on the PEI drivers for the platform for communication to the devices


-  Determine boot mode
  -  S3 and S5 are the most common modes
  -  Recovery mode
-  Low-level initialization of the platform
  -  Find FVs that contain DXE
-  Discover and initialize main memory
-  Transfer control according to boot mode
  -  If S5 hands control to DXE
  -  If S3 uses waking vector


-  Platform PEI code can be divided into 3 phases:
  1.  Pre-Memory Initialization
    -  Initialize the memory controller
    -  Detect boot mode.
    -  Detect video adapter
  2.  Memory Initialization (MRC)
    -  Install  UEFI Memory.
    -  Capsule coalesce, Capsule Boot.
    -  Create HOB of system memory.
  3.  Post-Memory initialization
    -  PCH initialization after MRC.
    -  SIO initialization.
    - Install ResetSystem and FinvFv PPI, if  recovery boot mode.
    - Set MTRR for PEI
    - Create FV HOB and Flash HOB
    - Install RecoveryModule and AtaController PPI  if  recovery boot mode.


---?image=/assets/images/slides/Slide71.JPG
@title[PEI Phase – MAX has 2 PEIM Modules ]
<p align="right"><span class="gold" >PEI Phase – MAX has 2 PEIM Modules </span></p>

Note:
-   The main platform PEI code is in a subdirectory of the platform package. (PlatformPei)
-  It references PEIMs in other packages
-  PEI code is dependant on the PEI drivers for the platform for communication to the devices



---?image=/assets/images/slides/Slide73.JPG
@title[PEI Phase – MAX has 2 PEIM Modules ]
<p align="right"><span class="gold" >PEI Phase – MAX has 2 PEIM Modules </span></p>

Note:
-   The main platform PEI code is in a subdirectory of the platform package. (PlatformPei)
-  It references PEIMs in other packages
-  PEI code is dependant on the PEI drivers for the platform for communication to the devices


---?image=/assets/images/slides/Slide75.JPG
@title[Recommended PEI Addresses]
<p align="right"><span class="gold" >Recommended PEI Addresses </span></p>

Note:

-  Platform information commonly used in PEI
  -  Base addresses
  -  GPIO addresses
  -  SMBUS address
  -  Memory configuration (channels, ports, etc…)
  -  ACPI settings (base address register, etc…)
-  Goal is to extract these concepts in PCD entries and make them changeable through DSC without having to modify module source



---?image=/assets/images/slides/Slide77.JPG
@title[How to search Workspace]
<p align="right"><span class="gold" >How to search for Addresses in the Workspace</span></p>

Note:

-  How to search for GPIOs for NewProjectPkg 
 -    KEY - search the workspace for a string and work back to Data structures declaring then use the DSC for which moduls are included


---?image=/assets/images/slides/Slide79.JPG
<!-- .slide: data-transition="none" -->
@title[How to search for GPIOs for NewProjectPkg]
<p align="right"><span class="gold" >How to search for GPIOs for NewProjectPkg</span></p>



+++?image=/assets/images/slides/Slide80.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[How to search for GPIOs for NewProjectPkg 02]
<p align="right"><span class="gold" >How to search for GPIOs for NewProjectPkg</span></p>

Note:


+++?image=/assets/images/slides/Slide81.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[How to search for GPIOs for NewProjectPkg 03]
<p align="right"><span class="gold" >How to search for GPIOs for NewProjectPkg</span></p>

Note:


+++?image=/assets/images/slides/Slide82.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[How to search for GPIOs for NewProjectPkg 04]
<p align="right"><span class="gold" >How to search for GPIOs for NewProjectPkg</span></p>

Note:


+++?image=/assets/images/slides/Slide83.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[How to search for GPIOs for NewProjectPkg 05]
<p align="right"><span class="gold" >How to search for GPIOs for NewProjectPkg</span></p>

Note:



---?image=/assets/images/slides/Slide85.JPG
<!-- .slide: data-transition="none" -->
@title[PEI Memory Base Address, PCD Example  ]
<p align="right"><span class="gold" >PEI Memory Base Address, PCD Example  </span></p>

Note:
-  Lets take a look at a PEI PCD example

-  Here we see that we are using the SMBUS  base address

-  It IS Defined in ICH X Package DEC
	  -  [PcdsFixedAtBuild.common]
	  -  gEfiIchTokenSpaceGuid.PcdIchSmbusIoPortBaseAddress|0xEFFF|UINT16|0x3000000f

-  The Module INF lists which PCDs get accessed
	-  [Pcd]
	-  gEfiIchTokenSpaceGuid.PcdIchSmbusIoPortBaseAddress

-  The Value to use is in the Project New Package DSC
	-  [PcdsFixedAtBuild.IA32]
	-  gEfiIchTokenSpaceGuid.PcdIchSmbusIoPortBaseAddress|0xEFA0

-  The example in the code:
  -  PEI - Referenced in the PEI code IntelIchXLib.c
  -  	PciWrite32 (PCI_ICH_SMBUS_ADDRESS (R_ICH_SMBUS_SMB_BASE), 
			-  (UINT32) PcdGet16 (PcdIchSmbusIoPortBase


+++?image=/assets/images/slides/Slide86.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PEI Memory Base Address, PCD Example 02  ]
<p align="right"><span class="gold" >PEI Memory Base Address, PCD Example  </span></p>


Note:


+++?image=/assets/images/slides/Slide87.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PEI Memory Base Address, PCD Example 03  ]
<p align="right"><span class="gold" >PEI Memory Base Address, PCD Example  </span></p>


Note:


+++?image=/assets/images/slides/Slide88.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PEI Memory Base Address, PCD Example 04  ]
<p align="right"><span class="gold" >PEI Memory Base Address, PCD Example  </span></p>


Note:


+++?image=/assets/images/slides/Slide89.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PEI Memory Base Address, PCD Example 05 ]
<p align="right"><span class="gold" >PEI Memory Base Address, PCD Example  </span></p>


Note:



---?image=/assets/images/slides/Slide91.JPG
@title[Critical PEIMs]
<p align="right"><span class="gold" >Critical PEIMs  </span></p>


Note:
-  So what are the Critical PEIMs?


-  These are the minimum set of PEI components that must be dispatched during the PEI.
-  The list here is those PEIMs that encapsulate those. The order shown here is not the dispatch order.  The DXE IPL PEIM is dispatched last
-  The CPU PEIM installs the CPU_IO PPI that provides CPU IO functions
-  The DXE IPL PEIM hands off control from the PEI Core to DXE
-  The PCI PEIM provides basic PCI functions to PEI
-  The Stall PEIM provides a sleep or wait function
-  The Status Code PEIM is for debug messages (Port80) and serial port if in debug mode
-  The SMBUS PEIM initializes and provides SMBUS access
-  The Memory Control PEIMs read the SPD and initialize/configure memory

-  Additional platform PEIMs for flash map layout, boot policy determination, fan control and misc chipset initialization
-  Platform Configurations Database PCD



-  Porting Key with respect to the Copied Project/platform
  -  The ones in green will typically not require changes if your platform is PCAT based.
  -  The ones in orange  will need attention if your platform is different that the reference platforms.



---?image=/assets/images/slides/Slide93.JPG
@title[Initial Program Load (IPL) PEIM for DXE]
<p align="right"><span class="gold" >Initial Program Load (IPL) PEIM for DXE  </span></p>
<br>
<div class="left">
<span style="font-size:0.8em" > &nbsp;</span>
</div>
<div class="right">
<br>
@ul[no-bullet]
-  <font color="#FFFF00">&nbsp;&nbsp;<b>Creates HOBs </b></font> <br><br>
-  <font color="white">&nbsp;&nbsp;<b>Locates DXE main </b></font>  <BR><br>
-  <font color="#ffc000">&nbsp;&nbsp;<b>Switch Stacks</b></font>  <br><br>
-  <font color="cyan">&nbsp;&nbsp;<b>&rarr;&nbsp;DxeMain() </b></font> 
@ulend
</div>			

Note:
-  The DXE IPL PEIM should not require porting, but  knowing what is does it important.  This is a good place for a breakpoint and starting to debug.  For example, if porting didn’t work this is where it will fail.

-  The DXE IPL PEIM performs several tasks

-  Shadows DXE IPL into permanent memory to allow sharing of the decompression algorithm and several other library routines (e.g. security)
-  Allocates 128KB of stack for the DXE phase
-  Creates HOBs for passing library routines and the firmware volumes discovered during the PEI phase. Most commonly this is the main FV and any other FVs that DXE will use to load drivers from (for example backup block)
-  If S3, then the OS waking vector is called
-  Locate DXE Main in the FVs
-  If not S3 then switch stacks and call DXE Main


-  The last PEIM to execute
-  Shadows into permanent memory
-  Shares data from PEI phase with DXE
-  Creates a stack for DXE Phase
-  Creates HOBs
-  Calls S3 vector if appropriate
-  Locate DXE Main
-  Switch stack and call DXE Main



---?image=/assets/images/slides/Slide96.JPG
@title[DXE Phase]
<p align="center"><span class="gold" >DXE Phase </span></p>
<div class="left-1">
<span style="font-size:0.8em" > &nbsp;</span>
</div>
<div class="right-1">
<br>
<br>
<ul style="list-style-type:none">
  <li><span style="font-size:0.9em" ><font color="yellow"> Main platform DXE code in subdirectories of the platform package containing “DXE” in the name</font> </span></li><br>
  <li><span style="font-size:0.9em" ><font color="cyan">Establish Architectural Protocols </font> </span></li><br>
  <li><span style="font-size:0.9em" ><font color="#ffc000">Install any required DXE / UEFI Drivers </font> </span></li>
</ul>
</div>		

Note:

-  The main platform DXE code is in subdirectories of the platform package having “DXE” in the directory name (i.e. PciPlatformDxe)
   -  It will reference other packages DXE modules
-  Establish the architectural protocols
  -  Isolate platform specific hardware (e.g., RTC)
  -  Provide support for boot and runtime services
  -  Low level protocols that support DXE APIs
  -  Directly called by DXE core
-  Install any required DXE and then the UEFI Drivers


---?image=/assets/images/slides/Slide99.JPG
@title[DXE Architectural Protocols ]
<p align="right"><span class="gold" >DXE Architectural Protocols (AP)</span></p>


Note:

-  Isolate platform specific hardware (e.g., RTC)
-  Provide support for boot and runtime services
-  Low level protocols that support DXE APIs



---?image=/assets/images/slides/Slide101.JPG
@title[How to Search for AP Modules  top]
<p align="right"><span class="gold" >How to Search for AP Modules </span></p>



---?image=/assets/images/slides/Slide103.JPG
<!-- .slide: data-transition="none" -->
@title[How to Search for AP Modules 01 ]
<p align="right"><span class="gold" >How to Search for AP Modules in the Project </span></p>

Note:
-  Search the Work Space .INF files  for the Architectural Protocols  - key word “Produces”
  -  gEfiCpuArchProtocolGuid 
<pre>
 UefiCpuPkg/CpuDxe/				##PRODUCES
 Vlv2DeviceRefCodePkg/ValleyView2Soc/CPU/CpuInit/Dxe/
 IA32FamilyCpuPkg/CpuArchDxe	##PRODUCES
</pre>

-  Find which module Install the protocol (.i.e Search .c )
  -  gEfiCpuArchProtocolGuid 
-  Check the NewProjectPkg .DSC to see which .INF is included in the [Components] section
-  Vlv2DeviceRefCodePkg/ValleyView2Soc/CPU/CpuInit/Dxe/MpCpu.inf




+++?image=/assets/images/slides/Slide104.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[How to Search for AP Modules 02 ]
<p align="right"><span class="gold" >How to Search for AP Modules in the Project </span></p>

Note:
-  Search the Work Space .INF files  for the Architectural Protocols  - key word “Produces”
  -  gEfiCpuArchProtocolGuid 
<pre>
 UefiCpuPkg/CpuDxe/				##PRODUCES
 Vlv2DeviceRefCodePkg/ValleyView2Soc/CPU/CpuInit/Dxe/
 IA32FamilyCpuPkg/CpuArchDxe	##PRODUCES
</pre>

-  Find which module Install the protocol (.i.e Search .c )
  -  gEfiCpuArchProtocolGuid 
-  Check the NewProjectPkg .DSC to see which .INF is included in the [Components] section
-  Vlv2DeviceRefCodePkg/ValleyView2Soc/CPU/CpuInit/Dxe/MpCpu.inf


+++?image=/assets/images/slides/Slide105.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[How to Search for AP Modules 03 ]
<p align="right"><span class="gold" >How to Search for AP Modules in the Project </span></p>

Note:
-  Search the Work Space .INF files  for the Architectural Protocols  - key word “Produces”
  -  gEfiCpuArchProtocolGuid 
<pre>
 UefiCpuPkg/CpuDxe/				##PRODUCES
 Vlv2DeviceRefCodePkg/ValleyView2Soc/CPU/CpuInit/Dxe/
 IA32FamilyCpuPkg/CpuArchDxe	##PRODUCES
</pre>

-  Find which module Install the protocol (.i.e Search .c )
  -  gEfiCpuArchProtocolGuid 
-  Check the NewProjectPkg .DSC to see which .INF is included in the [Components] section
-  Vlv2DeviceRefCodePkg/ValleyView2Soc/CPU/CpuInit/Dxe/MpCpu.inf


+++?image=/assets/images/slides/Slide106.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[How to Search for AP Modules 04 ]
<p align="right"><span class="gold" >How to Search for AP Modules in the Project </span></p>

Note:
-  Search the Work Space .INF files  for the Architectural Protocols  - key word “Produces”
  -  gEfiCpuArchProtocolGuid 
<pre>
 UefiCpuPkg/CpuDxe/				##PRODUCES
 Vlv2DeviceRefCodePkg/ValleyView2Soc/CPU/CpuInit/Dxe/
 IA32FamilyCpuPkg/CpuArchDxe	##PRODUCES
</pre>

-  Find which module Install the protocol (.i.e Search .c )
  -  gEfiCpuArchProtocolGuid 
-  Check the NewProjectPkg .DSC to see which .INF is included in the [Components] section
-  Vlv2DeviceRefCodePkg/ValleyView2Soc/CPU/CpuInit/Dxe/MpCpu.inf



---?image=/assets/images/slides/Slide113.JPG
<!-- .slide: data-transition="none" -->
@title[Platform-Dependent DXE Drivers ]
<p align="right"><span class="gold" >Platform-Dependent DXE Drivers</span></p>

Note:

-  MinnowBoard Max
  -  <Memory Cntrl> Vlv2DeviceRefCodePkg/ValleyView2Soc/NorthCluster
  -  <PchX South> Vlv2DeviceRefCodePkg/ValleyView2Soc/SouthCluster


+++?image=/assets/images/slides/Slide114.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Platform-Dependent DXE Drivers 02]
<p align="right"><span class="gold" >Platform-Dependent DXE Drivers</span></p>

Note:

-  MinnowBoard Max
  -  <Memory Cntrl> Vlv2DeviceRefCodePkg/ValleyView2Soc/NorthCluster
  -  <PchX South> Vlv2DeviceRefCodePkg/ValleyView2Soc/SouthCluster


---?image=/assets/images/slides/Slide116.JPG
@title[MinnowBoard Max SoC Specific Modules ]
<p align="right"><span class="gold" >MinnowBoard Max SoC Specific Modules</span></p>

Note:
-  Vlv2DeviceRefCodePkg/
  -  ValleyView2Soc/ 
    -  CPU
    -  NorthCluster
    -  SouthCluster

-  Other SOC 
	  -  Broxton Silicon Ref package
	  -  BroxtonSoc/BroxtonSiPkg/ 



---?image=/assets/images/slides/Slide118.JPG
<!-- .slide: data-transition="none" -->
@title[DXE Base Address, PCD Example]
<p align="right"><span class="gold" >DXE Base Address, PCD Example</span></p>

Note:
-  Example of a PCD during DXE

-  Defined in ICH X Package DEC
	-  [PcdsDynamic.common]
     -  	gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0|UINT8|0x40000016
-  The Module INF lists which PCDs get accessed
	  -  [Pcd]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs
-  The Value to use in New Project Package DSC
	  -  [PcdsDynamicDefault.common.DEFAULT]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0

-  Here is an example used in the CODE
-  DXE - Referenced in the DXE code in NewProjectPkg/ SetupDxe/Platform.c
	 
  -  	IchSataPataConfigs.Uint8 = PcdGet8(PcdIchSataPataConfigs);
  -  	PcdSet8(PcdIchSataPataConfigs, IchSataPataConfigs.Uint8);


+++?image=/assets/images/slides/Slide119.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[DXE Base Address, PCD Example 02]
<p align="right"><span class="gold" >DXE Base Address, PCD Example</span></p>

Note:
-  Example of a PCD during DXE

-  Defined in ICH X Package DEC
	-  [PcdsDynamic.common]
     -  	gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0|UINT8|0x40000016
-  The Module INF lists which PCDs get accessed
	  -  [Pcd]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs
-  The Value to use in New Project Package DSC
	  -  [PcdsDynamicDefault.common.DEFAULT]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0

-  Here is an example used in the CODE
-  DXE - Referenced in the DXE code in NewProjectPkg/ SetupDxe/Platform.c
	 
  -  	IchSataPataConfigs.Uint8 = PcdGet8(PcdIchSataPataConfigs);
  -  	PcdSet8(PcdIchSataPataConfigs, IchSataPataConfigs.Uint8);

  

+++?image=/assets/images/slides/Slide120.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[DXE Base Address, PCD Example 03]
<p align="right"><span class="gold" >DXE Base Address, PCD Example</span></p>

Note:
-  Example of a PCD during DXE

-  Defined in ICH X Package DEC
	-  [PcdsDynamic.common]
     -  	gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0|UINT8|0x40000016
-  The Module INF lists which PCDs get accessed
	  -  [Pcd]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs
-  The Value to use in New Project Package DSC
	  -  [PcdsDynamicDefault.common.DEFAULT]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0

-  Here is an example used in the CODE
-  DXE - Referenced in the DXE code in NewProjectPkg/ SetupDxe/Platform.c
	 
  -  	IchSataPataConfigs.Uint8 = PcdGet8(PcdIchSataPataConfigs);
  -  	PcdSet8(PcdIchSataPataConfigs, IchSataPataConfigs.Uint8);


+++?image=/assets/images/slides/Slide121.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[DXE Base Address, PCD Example 04]
<p align="right"><span class="gold" >DXE Base Address, PCD Example</span></p>

Note:
-  Example of a PCD during DXE

-  Defined in ICH X Package DEC
	-  [PcdsDynamic.common]
     -  	gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0|UINT8|0x40000016
-  The Module INF lists which PCDs get accessed
	  -  [Pcd]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs
-  The Value to use in New Project Package DSC
	  -  [PcdsDynamicDefault.common.DEFAULT]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0

-  Here is an example used in the CODE
-  DXE - Referenced in the DXE code in NewProjectPkg/ SetupDxe/Platform.c
	 
  -  	IchSataPataConfigs.Uint8 = PcdGet8(PcdIchSataPataConfigs);
  -  	PcdSet8(PcdIchSataPataConfigs, IchSataPataConfigs.Uint8);


+++?image=/assets/images/slides/Slide122.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[DXE Base Address, PCD Example 05]
<p align="right"><span class="gold" >DXE Base Address, PCD Example</span></p>

Note:
-  Example of a PCD during DXE

-  Defined in ICH X Package DEC
	-  [PcdsDynamic.common]
     -  	gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0|UINT8|0x40000016
-  The Module INF lists which PCDs get accessed
	  -  [Pcd]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs
-  The Value to use in New Project Package DSC
	  -  [PcdsDynamicDefault.common.DEFAULT]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0

-  Here is an example used in the CODE
-  DXE - Referenced in the DXE code in NewProjectPkg/ SetupDxe/Platform.c
	 
  -  	IchSataPataConfigs.Uint8 = PcdGet8(PcdIchSataPataConfigs);
  -  	PcdSet8(PcdIchSataPataConfigs, IchSataPataConfigs.Uint8);


+++?image=/assets/images/slides/Slide123.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[DXE Base Address, PCD Example 06]
<p align="right"><span class="gold" >DXE Base Address, PCD Example</span></p>

Note:
-  Example of a PCD during DXE

-  Defined in ICH X Package DEC
	-  [PcdsDynamic.common]
     -  	gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0|UINT8|0x40000016
-  The Module INF lists which PCDs get accessed
	  -  [Pcd]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs
-  The Value to use in New Project Package DSC
	  -  [PcdsDynamicDefault.common.DEFAULT]
	    -  gEfiIchTokenSpaceGuid.PcdIchSataPataConfigs|0

-  Here is an example used in the CODE
-  DXE - Referenced in the DXE code in NewProjectPkg/ SetupDxe/Platform.c
	 
  -  	IchSataPataConfigs.Uint8 = PcdGet8(PcdIchSataPataConfigs);
  -  	PcdSet8(PcdIchSataPataConfigs, IchSataPataConfigs.Uint8);

---?image=/assets/images/slides/Slide125.JPG
@title[BDS Phase:]
<p align="center"><span class="gold" >BDS Phase:</span></p>
 
<div class="left-1">
<span style="font-size:0.8em" > &nbsp;</span>
</div>
<div class="right-1">
<br>
<br>
<ul style="list-style-type:none">
  <li><span style="font-size:0.9em" ><font color="white">Detect console devices (input and output) </font> </span></li><br>
  <li><span style="font-size:0.9em" ><font color="cyan">Check enumeration of all devices’ preset </font> </span></li><br>
  <li><span style="font-size:0.9em" ><font color="white">Detect boot policy</font> </span></li><br>
  <li><span style="font-size:0.9em" ><font color="cyan">Ensure BIOS “front page” is loaded </font> </span></li>

  </ul>
</div>		

Note:
 
-  Detect console devices (input and output)

-  Check enumeration of all devices preset
-  another Note; BIOS must have device drivers to enumerate

-  Detection of boot policy

-  Loading of BIOS “front page”
-  Splash screen logo, messages to user, etc.


---?image=/assets/images/slides/Slide128.JPG
@title[BDS Phase - stack]
<p align="right"><span class="gold" >BDS Phase</span></p>
 
Note:

-  Here is a picture of the protocol stack for the serial terminal console services. This details the protocols that are necessary for getting output on the serial terminal.

-  UEFI and the framework do not directly hard code input/output or console devices to another driver or program. They instead rely upon console devices to produce a Simple Text Input and Simple Text Output protocol. They consume from those protocols. Thus you can write your application free of worry where input and output will be going. 

-  To allow many devices to produce input and output, there is a virtual console or console splitter that gathers input from different devices and sends output to different devices. Thus the BDS or UEFI Shell is not directly connected to VGA or serial port. It sends output to the virtual console which in turns send that output to any device that is connected to it that has published the Simple Text Output Protocol.

-  In the porting aspect, once ISA I/O protocol driver is ported and the underlying protocols it depends on, the Serial I/O driver can be ported and then the BDS and/or UEFI shell can be used as-is to continue with your porting and debugging effort.



---?image=/assets/images/slides/Slide130.JPG
@title[Serial Terminal Console Drivers]
<p align="right"><span class="gold" >Serial Terminal Console Drivers</span></p>
 
Note:

-  Here is a table of the drivers used. The drivers in green do not require any changes for your platform. You may have changes in your ISA serial if the UARTs are different than the normal PCAT UARTs

-  The Console splitter may require changes if your default serial port is not the same as the default one – baud rate, COM port, etc.

-  The orange ones (or chipset specific) are the base protocols that need platform porting if yours is different than our reference implementation
 
 


---?image=/assets/images/slides/Slide132.JPG
<!-- .slide: data-transition="none" -->
@title[Porting Serial Terminal Console]
<p align="right"><span class="gold" >Porting Serial Terminal Console</span></p>
 
Note:
-  Example platform
-  specific location
  -  EDK II Open
  -  Source location


+++?image=/assets/images/slides/Slide133.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Serial Terminal Console 02]
<p align="right"><span class="gold" >Porting Serial Terminal Console</span></p>
 
Note:
-  Example platform
-  specific location
  -  EDK II Open
  -  Source location



---?image=/assets/images/slides/Slide135.JPG
@title[Porting Task List Section]
<p align="center"><span class="gold" ><b>Porting Task List</b></span></p>


Note:
- Section 5 of the Porting Task List
 -  Update build text files with libraries, ported modules, and PCD values to configure modules


---?image=/assets/images/slides/Slide137.JPG
@title[Build Text Files for the Platform]
<p align="right"><span class="gold" >Build Text Files for the Platform</span></p>
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<span style="font-size:0.5em" >Check the <a href="https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Specifications">EDK II Specifications</a> </span>

Note:
-  Specs:
  -  https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Specifications

- PCD Values - Library classes -	NewProjectPkg.DSC
- Flash Map layout 	-	NewProjectPkg.FDF
- Defines for a platform -	NewProjectPkg.DEC



---?image=/assets/images/slides/Slide139.JPG
@title[Update the New Project DEC File]
<p align="right"><span class="gold" >Update the New Project DEC File</span></p>
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<span style="font-size:0.5em" > Example DEC file for NewProjectPkg - Next slide</span>

Note:


-  Update the PCD used by the New Project Package 
-  Update for the Libraries and Protocols used by the New Project Package
-  See EDK II DEC File Specification for more details and examples 



+++?code=sample/NewProjectPORT/NewProjectPkg.dec&lang=shell&title=Example: DEC file


Note:
 This is an example of the NewProjectPkg.dec file


---?image=/assets/images/slides/Slide141.JPG
@title[Update the New Project DSC File]
<p align="right"><span class="gold" >Update the New Project DSC File</span></p>
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<br> 
<span style="font-size:0.5em" > Example DSC file for NewProjectPkg - Next slide</span>

Note:

-  Update to define all libraries, components and/or modules that will be used by the New Project package
-  Update the PCD Values for the New Project 
-  Update any library classes
-  See EDK II DSC File Specification for more details and examples 


+++?code=sample/NewProjectPORT/NewProjectPkg.dsc&lang=shell&title=Example: DSC file


Note:
 This is an example of the NewProjectPkg.dsc file



---?image=/assets/images/slides/Slide143.JPG
<!-- .slide: data-transition="none" -->
@title[Update the New Project FDF File]
<p align="right"><span class="gold" >Update the New Project FDF File</span></p>

Note:
-  Rules for combining binaries (Firmware Image) built from a DSC file
-  PCDs set in the FDF file for Addresses, Sizes, and other "fixed" information needed to define or create the flash image 
-  See EDK II FDF File Specification for more details and examples 

-  Used to define what components or modules are placed within a flash device (FD) file
-  Defines order the components and modules are positioned within the image
-  Consists of define statements, set statements and module statements (INF files to be used)


+++?image=/assets/images/slides/Slide145.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Update the New Project FDF File Layout]
<p align="right"><span class="gold" >Update the New Project FDF File - Layout</span></p>



Note:
Flash Device Configuration Common Layout File (.fdf)


+++?code=sample/NewProjectPORT/NewProjectPkg.fdf&lang=shell&title=Example: FDF file


Note:
 This is an example of the NewProjectPkg.fdf file

 
+++
@title[FDF File Example]
<p align="right"><span class="gold" >FDF File Example</span></p>


```C
[Fv.Root]
FvAlignment = 64
ERASE_POLARITY = 1
MEMORY_MAPPED = TRUE
STICKY_WRITE = TRUE
. . .
INF VERSION = "1" $(WS)/EdkNt32Pkg/ Dxe/WinNtThunk/Cpu/Cpu.inf
FILE DXE_CORE = B5596C75-37A2-4. . .{
  SECTION COMPRESS { . . .}


DEFINE DC = $(WS)/Build/NewProjectPkg 	/DEBUG_MYTOOLS
    SECTION PE32 = $(DC)/B5596C75-3 . . .     	-DxeCore.efi
    SECTION VERSION "1.2.3"
   }
}
FILE FV_IMAGE = EF41A0E1-40B1-481 . . .{
  FvAlignment = 512K
  WRITE_POLICY_RELIABLE = TRUE
  SECTION GUIDED 3EA022A4-1439-4 . . . {
    SECTION FV_IMAGE = Dxe {
    APRIORI DXE {
        INF NewProject/a/a.inf
        INF MdePkg/x/y/z.inf
        INF NewProject/a/b/b.inf
    }
      INF a/d/d.inf
      . . . 
    }
  }
DEFINE SAMPLE = MdeModulePkg/Sample 
INF $(SAMPLE)/Universal/Network/ Ip4Dxe/Ip4Dxe.inf
INF $(SAMPLE)/Universal/Network/ Ip4ConfigDxe/Ip4ConfigDxe.inf 
INF $(SAMPLE)/Universal/Network/ Udp4Dxe/Udp4Dxe.inf 
INF $(SAMPLE)/Universal/Network/ Tcp4Dxe/Tcp4Dxe.inf 
INF $(SAMPLE)/Universal/Network/ Dhcp4Dxe/Dhcp4Dxe.inf 
INF $(SAMPLE)/Universal/Network/ Mtftp4Dxe/Mtftp4Dxe.inf 
INF $(SAMPLE)/Universal/Network/ SnpNt32Dxe/SnpNt32Dxe.inf 

```


---?image=/assets/images/slides/Slide148.JPG
@title[Porting Task List Section 06]
<p align="center"><span class="gold" ><b>Porting Task List</b></span></p>


Note:
- Section 6 of the Porting Task List
 -  Minimums for UEFI Shell


---?image=/assets/images/slides/Slide150.JPG
@title[Minimum Drivers for UEFI Shell]
<p align="right"><span class="gold" >Minimum Drivers for UEFI Shell</span></p>

Note:
Here we have a summary of the drivers that will most likely need changing for your port to a new platform to bring up the EFI shell. As you can see the list is not that long. If your platform is similar to one of our reference platforms (same chipset typically) then your porting effort will mostly be in the area of MRC, Super I/O and PCI infrastructure (servers may have multiple root bus bridges)

The goodness about this is that you can bring the shell up and then via serial port interact with the shell to load and test new drivers as well as your port to this point.

-  MinnowBoard Max
  -  <Memory Cntrl North> Vlv2DeviceRefCodePkg/ValleyView2Soc/NorthCluster
  -  <I/O Cntrl South> Vlv2DeviceRefCodePkg/ValleyView2Soc/SouthCluster




---?image=/assets/images/slides/Slide152.JPG
@title[Minimum Libraries for UEFI Shell]
<p align="right"><span class="gold" >Minimum Libraries for UEFI Shell</span></p>

Note:
Just be aware of Shell libraries that would be interfacing with the platform for porting

-  MinnowBoard Max
  -  <I/O Cntrl South> Vlv2DeviceRefCodePkg/ValleyView2Soc/SouthCluster



---?image=/assets/images/slides/Slide154.JPG
<!-- .slide: data-transition="none" -->
@title[Porting Summary: New Package Directory]
<p align="right"><span class="gold" >Porting Summary: New Package Directory</span></p>

Note:


+++?image=/assets/images/slides/Slide155.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Summary: New Package Directory 02]
<p align="right"><span class="gold" >Porting Summary: New Package Directory</span></p>

Note:

+++?image=/assets/images/slides/Slide156.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Summary: New Package Directory 03]
<p align="right"><span class="gold" >Porting Summary: New Package Directory</span></p>

Note:


+++?image=/assets/images/slides/Slide157.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Summary: New Package Directory 04]
<p align="right"><span class="gold" >Porting Summary: New Package Directory</span></p>

Note:

+++?image=/assets/images/slides/Slide158.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Summary: New Package Directory 05]
<p align="right"><span class="gold" >Porting Summary: New Package Directory</span></p>

Note:

+++?image=/assets/images/slides/Slide159.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Porting Summary: New Package Directory 06]
<p align="right"><span class="gold" >Porting Summary: New Package Directory</span></p>

Note:


  


  
---  
@title[Summary]
<BR>
### <p align="center"><span class="gold"   >Summary </span></p><br>
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;Define the porting task list for porting existing platforms in EDK II in order to boot to the UEFI Shell</span> </li>
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Explain the EDK II infrastructure, porting libraries, library classes, PCDs, and directory structures</span></li>
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Determine the necessary porting for each phase of a new EDK II platform Project</span> </li>
</ul>


---?image=assets/images/gitpitch-audience.jpg
@title[Questions]
<br>
![Questions](/assets/images/questions.JPG) 


---?image=assets/images/gitpitch-audience.jpg
@title[Logo Slide]
<br><br><br>
![Logo Slide](/assets/images/TianocoreLogo.png =10x)


---
@title[Acknowledgements]
#### <p align="center"><span class="gold"   >Acknowledgements</span></p>

```c++
/**
Redistribution and use in source (original document form) and 'compiled' forms (converted
to PDF, epub, HTML and other formats) with or without modification, are permitted provided
that the following conditions are met:

Redistributions of source code (original document form) must retain the above copyright 
notice, this list of conditions and the following disclaimer as the first lines of this 
file unmodified.

Redistributions in compiled form (transformed to other DTDs, converted to PDF, epub, HTML
and other formats) must reproduce the above copyright notice, this list of conditions and 
the following disclaimer in the documentation and/or other materials provided with the 
distribution.

THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR IMPLIED 
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND 
FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL TIANOCORE PROJECT BE 
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES 
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, 
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, 
WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF ADVISED OF THE POSSIBILITY 
OF SUCH DAMAGE.

Copyright (c) 2018, Intel Corporation. All rights reserved.
**/

```
