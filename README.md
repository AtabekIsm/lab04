armvo@LAPTOP-V7PSSN9N:~$ export GITHUB_USERNAME=AtabekIsm
armvo@LAPTOP-V7PSSN9N:~$ export GITHUB_TOKEN=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
armvo@LAPTOP-V7PSSN9N:~$ cd ${GITHUB_USERNAME}/workspace
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ pushd .
~/AtabekIsm/workspace ~/AtabekIsm/workspace
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ source scripts/activate
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ echo "source $HOME/.rvm/scripts/rvm" >> scripts/activate
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ . scripts/activate
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ rvm autolibs disable
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ rvm use 2.4.2 --default
Using /home/armvo/.rvm/gems/ruby-2.4.2
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab03 projects/lab04
fatal: destination path 'projects/lab04' already exists and is not an empty directory.
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ cd projects/lab04
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git remote remove origin
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab04
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ cat > .travis.yml <<EOF
language: cpp
EOF
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ cat >> .travis.yml <<EOF
> script:
- cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
- cmake --build _build
- cmake --build _build --target install
EOF
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ cat >> .travis.yml <<EOF
> addons:
  apt:
    sources:
      - george-edison55-precise-backports
    packages:
      - cmake
      - cmake-data
EOF
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ travis login --github-token ${GITHUB_TOKEN}

  ________                                 __
 /        |                               /  |
 ########/ ______    ______    __     __  ##/    _______
    ## |  /      \  /      \  /  \   /  | /  |  /       |
    ## | /######  | ######  | ##  \ /##/  ## | /#######/
    ## | ## |  ##/  /    ## |  ##  /##/   ## | ##      \
    ## | ## |      /####### |   ## ##/    ## |  ######  |
    ## | ## |      ##    ## |    ###/     ## | /     ##/
    ##/  ##/        #######/      #/      ##/  #######/

    TRajectory Analyzer and VISualizer  -  Open-source free software under GNU GPL v3

    Copyright (c) Martin Brehm      (2009-2022), University of Halle (Saale)
                  Martin Thomas     (2012-2022)
                  Sascha Gehrke     (2016-2022), University of Bonn
                  Barbara Kirchner  (2009-2022), University of Bonn

    http://www.travis-analyzer.de

    Please cite: J. Chem. Phys. 2020, 152 (16), 164105.         (DOI 10.1063/5.0005078 )
                 J. Chem. Inf. Model. 2011, 51 (8), 2007-2023.  (DOI 10.1021/ci200217w )

    There is absolutely no warranty on any results obtained from TRAVIS.

 #  Running on LAPTOP-V7PSSN9N at Sun May 11 22:12:46 2025 (PID 948)
 #  Running in /home/armvo/AtabekIsm/workspace/projects/lab04
 #  Version: Jul 29 2022, built at Jan 14 2023, 12:32:45, compiler "12.2.0", GCC 12.2.0
 #  Target platform: Linux, __cplusplus=201703L, Compile flags: NEW_CHARGEVAR DEBUG_ARRAYS
 #  Compiled with OpenMP, but USE_OMP not switched on in "config.h"!
 #  Machine: x86_64, char=1b, int=4b, long=8b, addr=8b, 0xA0B0C0D0=D0,C0,B0,A0.
 #  Home: /home/armvo,  Executable: /usr/bin/travis
 #  Input from terminal,  Output to terminal

    >>> Please use a color scheme with dark background or specify "-nocolor"! <<<

    No configuration file found.
    Writing default configuration to /home/armvo/.travis.conf ...

Unknown parameter: "login".

    List of supported command line options:

      -p <file>       Load position data from specified trajectory file.
                      Format may be *.xyz, *.pdb, *.lmp (LAMMPS), HISTORY (DLPOLY), POSCAR/XDATCAR (VASP),
                                    *.gro, *.dcd, or *.prmtop/*.mdcrd (Amber).
                      The bqb format (*.bqb, *.btr, *.emp, *.blist) as well as *.voronoi are also supported.
      -vel <file>     Read atom velocities from a file in addition to the position trajectory.
                      Currently, only .xyz format is supported for velocity data.
      -i <file>       Read input from specified text file.
      -c <file>       Read and execute control file (experimental).
      cubetool        Execute the CubeTool for modifying Gaussian Cube files.
      -sankey <file>  Create Sankey diagrams (file name is optional).
      -ramanfrompola  Compute Raman spectra from existing polarizability time series.
      (de-)compress   Start built-in bqbtool (compress trajectories to BQB format).
      check           Check BQB file integrity.

      -config <file>  Load the specified configuration file.
      -stream         Treat input trajectory as a stream (e.g. named pipe): No fseek, etc.
      -showconf       Show a tree structure of the configuration file.
      -writeconf      Write the default configuration file, including all defines values.

      -verbose        Show detailed information about what's going on.
      -nocolor        Execute TRAVIS in monochrome mode (suitable for white background).
      -dimcolor       Use dim instead of bright colors.

      -credits        Display a list of persons who contributed to TRAVIS.
      -help, -?       Shows this help.

    If only one argument is specified, it is assumed to be the name of a trajectory file.
    If no argument is specified at all, TRAVIS asks for the trajectory file to open.

    Note: To show a list of all persons who contributed to TRAVIS,
          please add "-credits" to your command line arguments, or set the
          variable "SHOWCREDITS" to "TRUE" in your travis.conf file.

    Source code from other projects used in TRAVIS:
      - lmfit     from Joachim Wuttke
      - kiss_fft  from Mark Borgerding
      - voro++    from Chris Rycroft

    http://www.travis-analyzer.de

    Please cite all of the following articles for the analyses you have used:

  * For TRAVIS in general:

    "TRAVIS - A Free Analyzer for Trajectories from Molecular Simulation",
    M. Brehm, M. Thomas, S. Gehrke, B. Kirchner; J. Chem. Phys. 2020, 152 (16), 164105.   (DOI 10.1063/5.0005078 )

    "TRAVIS - A Free Analyzer and Visualizer for Monte Carlo and Molecular Dynamics Trajectories",
    M. Brehm, B. Kirchner; J. Chem. Inf. Model. 2011, 51 (8), pp 2007-2023.   (DOI 10.1021/ci200217w )

*** The End ***

armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ travis
[Renaming existing File travis.log to #1#travis.log ...OK.]

  ________                                 __
 /        |                               /  |
 ########/ ______    ______    __     __  ##/    _______
    ## |  /      \  /      \  /  \   /  | /  |  /       |
    ## | /######  | ######  | ##  \ /##/  ## | /#######/
    ## | ## |  ##/  /    ## |  ##  /##/   ## | ##      \
    ## | ## |      /####### |   ## ##/    ## |  ######  |
    ## | ## |      ##    ## |    ###/     ## | /     ##/
    ##/  ##/        #######/      #/      ##/  #######/

    TRajectory Analyzer and VISualizer  -  Open-source free software under GNU GPL v3

    Copyright (c) Martin Brehm      (2009-2022), University of Halle (Saale)
                  Martin Thomas     (2012-2022)
                  Sascha Gehrke     (2016-2022), University of Bonn
                  Barbara Kirchner  (2009-2022), University of Bonn

    http://www.travis-analyzer.de

    Please cite: J. Chem. Phys. 2020, 152 (16), 164105.         (DOI 10.1063/5.0005078 )
                 J. Chem. Inf. Model. 2011, 51 (8), 2007-2023.  (DOI 10.1021/ci200217w )

    There is absolutely no warranty on any results obtained from TRAVIS.

 #  Running on LAPTOP-V7PSSN9N at Sun May 11 22:15:36 2025 (PID 949)
 #  Running in /home/armvo/AtabekIsm/workspace/projects/lab04
 #  Version: Jul 29 2022, built at Jan 14 2023, 12:32:45, compiler "12.2.0", GCC 12.2.0
 #  Target platform: Linux, __cplusplus=201703L, Compile flags: NEW_CHARGEVAR DEBUG_ARRAYS
 #  Compiled with OpenMP, but USE_OMP not switched on in "config.h"!
 #  Machine: x86_64, char=1b, int=4b, long=8b, addr=8b, 0xA0B0C0D0=D0,C0,B0,A0.
 #  Home: /home/armvo,  Executable: /usr/bin/travis
 #  Input from terminal,  Output to terminal

    >>> Please use a color scheme with dark background or specify "-nocolor"! <<<

    Loading configuration from /home/armvo/.travis.conf ...

[Renaming existing File input.txt to #1#input.txt ...OK.]
    No trajectory file specified.
    Please use the "-p" flag to specify an input trajectory in the command line.

    Enter the file name of the trajectory file to open: [Quit]

    List of supported command line options:

      -p <file>       Load position data from specified trajectory file.
                      Format may be *.xyz, *.pdb, *.lmp (LAMMPS), HISTORY (DLPOLY), POSCAR/XDATCAR (VASP),
                                    *.gro, *.dcd, or *.prmtop/*.mdcrd (Amber).
                      The bqb format (*.bqb, *.btr, *.emp, *.blist) as well as *.voronoi are also supported.
      -vel <file>     Read atom velocities from a file in addition to the position trajectory.
                      Currently, only .xyz format is supported for velocity data.
      -i <file>       Read input from specified text file.
      -c <file>       Read and execute control file (experimental).
      cubetool        Execute the CubeTool for modifying Gaussian Cube files.
      -sankey <file>  Create Sankey diagrams (file name is optional).
      -ramanfrompola  Compute Raman spectra from existing polarizability time series.
      (de-)compress   Start built-in bqbtool (compress trajectories to BQB format).
      check           Check BQB file integrity.

      -config <file>  Load the specified configuration file.
      -stream         Treat input trajectory as a stream (e.g. named pipe): No fseek, etc.
      -showconf       Show a tree structure of the configuration file.
      -writeconf      Write the default configuration file, including all defines values.

      -verbose        Show detailed information about what's going on.
      -nocolor        Execute TRAVIS in monochrome mode (suitable for white background).
      -dimcolor       Use dim instead of bright colors.

      -credits        Display a list of persons who contributed to TRAVIS.
      -help, -?       Shows this help.

    If only one argument is specified, it is assumed to be the name of a trajectory file.
    If no argument is specified at all, TRAVIS asks for the trajectory file to open.

    Note: To show a list of all persons who contributed to TRAVIS,
          please add "-credits" to your command line arguments, or set the
          variable "SHOWCREDITS" to "TRUE" in your travis.conf file.

    Source code from other projects used in TRAVIS:
      - lmfit     from Joachim Wuttke
      - kiss_fft  from Mark Borgerding
      - voro++    from Chris Rycroft

    http://www.travis-analyzer.de

    Please cite all of the following articles for the analyses you have used:

  * For TRAVIS in general:

    "TRAVIS - A Free Analyzer for Trajectories from Molecular Simulation",
    M. Brehm, M. Thomas, S. Gehrke, B. Kirchner; J. Chem. Phys. 2020, 152 (16), 164105.   (DOI 10.1063/5.0005078 )

    "TRAVIS - A Free Analyzer and Visualizer for Monte Carlo and Molecular Dynamics Trajectories",
    M. Brehm, B. Kirchner; J. Chem. Inf. Model. 2011, 51 (8), pp 2007-2023.   (DOI 10.1021/ci200217w )

*** The End ***

armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ gem install travis
ERROR:  Loading command: install (LoadError)
        cannot load such file -- zlib
ERROR:  While executing gem ... (NoMethodError)
    undefined method `invoke_with_build_args' for nil:NilClass
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ sudo apt install zlib
[sudo] password for armvo:
Sorry, try again.
[sudo] password for armvo:
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
E: Unable to locate package zlib
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ sudo apt install -- zlib
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
E: Unable to locate package zlib
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ gem install travis
ERROR:  Loading command: install (LoadError)
        cannot load such file -- zlib
ERROR:  While executing gem ... (NoMethodError)
    undefined method `invoke_with_build_args' for nil:NilClass
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ travis --github-token ${GITHUB_TOKEN}
[Renaming existing File travis.log to #2#travis.log ...OK.]

  ________                                 __
 /        |                               /  |
 ########/ ______    ______    __     __  ##/    _______
    ## |  /      \  /      \  /  \   /  | /  |  /       |
    ## | /######  | ######  | ##  \ /##/  ## | /#######/
    ## | ## |  ##/  /    ## |  ##  /##/   ## | ##      \
    ## | ## |      /####### |   ## ##/    ## |  ######  |
    ## | ## |      ##    ## |    ###/     ## | /     ##/
    ##/  ##/        #######/      #/      ##/  #######/

    TRajectory Analyzer and VISualizer  -  Open-source free software under GNU GPL v3

    Copyright (c) Martin Brehm      (2009-2022), University of Halle (Saale)
                  Martin Thomas     (2012-2022)
                  Sascha Gehrke     (2016-2022), University of Bonn
                  Barbara Kirchner  (2009-2022), University of Bonn

    http://www.travis-analyzer.de

    Please cite: J. Chem. Phys. 2020, 152 (16), 164105.         (DOI 10.1063/5.0005078 )
                 J. Chem. Inf. Model. 2011, 51 (8), 2007-2023.  (DOI 10.1021/ci200217w )

    There is absolutely no warranty on any results obtained from TRAVIS.

 #  Running on LAPTOP-V7PSSN9N at Sun May 11 22:17:43 2025 (PID 997)
 #  Running in /home/armvo/AtabekIsm/workspace/projects/lab04
 #  Version: Jul 29 2022, built at Jan 14 2023, 12:32:45, compiler "12.2.0", GCC 12.2.0
 #  Target platform: Linux, __cplusplus=201703L, Compile flags: NEW_CHARGEVAR DEBUG_ARRAYS
 #  Compiled with OpenMP, but USE_OMP not switched on in "config.h"!
 #  Machine: x86_64, char=1b, int=4b, long=8b, addr=8b, 0xA0B0C0D0=D0,C0,B0,A0.
 #  Home: /home/armvo,  Executable: /usr/bin/travis
 #  Input from terminal,  Output to terminal

    >>> Please use a color scheme with dark background or specify "-nocolor"! <<<

    Loading configuration from /home/armvo/.travis.conf ...

[Renaming existing File input.txt to #2#input.txt ...OK.]
Unknown parameter: "--github-token".

    List of supported command line options:

      -p <file>       Load position data from specified trajectory file.
                      Format may be *.xyz, *.pdb, *.lmp (LAMMPS), HISTORY (DLPOLY), POSCAR/XDATCAR (VASP),
                                    *.gro, *.dcd, or *.prmtop/*.mdcrd (Amber).
                      The bqb format (*.bqb, *.btr, *.emp, *.blist) as well as *.voronoi are also supported.
      -vel <file>     Read atom velocities from a file in addition to the position trajectory.
                      Currently, only .xyz format is supported for velocity data.
      -i <file>       Read input from specified text file.
      -c <file>       Read and execute control file (experimental).
      cubetool        Execute the CubeTool for modifying Gaussian Cube files.
      -sankey <file>  Create Sankey diagrams (file name is optional).
      -ramanfrompola  Compute Raman spectra from existing polarizability time series.
      (de-)compress   Start built-in bqbtool (compress trajectories to BQB format).
      check           Check BQB file integrity.

      -config <file>  Load the specified configuration file.
      -stream         Treat input trajectory as a stream (e.g. named pipe): No fseek, etc.
      -showconf       Show a tree structure of the configuration file.
      -writeconf      Write the default configuration file, including all defines values.

      -verbose        Show detailed information about what's going on.
      -nocolor        Execute TRAVIS in monochrome mode (suitable for white background).
      -dimcolor       Use dim instead of bright colors.

      -credits        Display a list of persons who contributed to TRAVIS.
      -help, -?       Shows this help.

    If only one argument is specified, it is assumed to be the name of a trajectory file.
    If no argument is specified at all, TRAVIS asks for the trajectory file to open.

    Note: To show a list of all persons who contributed to TRAVIS,
          please add "-credits" to your command line arguments, or set the
          variable "SHOWCREDITS" to "TRUE" in your travis.conf file.

    Source code from other projects used in TRAVIS:
      - lmfit     from Joachim Wuttke
      - kiss_fft  from Mark Borgerding
      - voro++    from Chris Rycroft

    http://www.travis-analyzer.de

    Please cite all of the following articles for the analyses you have used:

  * For TRAVIS in general:

    "TRAVIS - A Free Analyzer for Trajectories from Molecular Simulation",
    M. Brehm, M. Thomas, S. Gehrke, B. Kirchner; J. Chem. Phys. 2020, 152 (16), 164105.   (DOI 10.1063/5.0005078 )

    "TRAVIS - A Free Analyzer and Visualizer for Monte Carlo and Molecular Dynamics Trajectories",
    M. Brehm, B. Kirchner; J. Chem. Inf. Model. 2011, 51 (8), pp 2007-2023.   (DOI 10.1021/ci200217w )

*** The End ***

armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ travis lint
[Renaming existing File travis.log to #3#travis.log ...OK.]

  ________                                 __
 /        |                               /  |
 ########/ ______    ______    __     __  ##/    _______
    ## |  /      \  /      \  /  \   /  | /  |  /       |
    ## | /######  | ######  | ##  \ /##/  ## | /#######/
    ## | ## |  ##/  /    ## |  ##  /##/   ## | ##      \
    ## | ## |      /####### |   ## ##/    ## |  ######  |
    ## | ## |      ##    ## |    ###/     ## | /     ##/
    ##/  ##/        #######/      #/      ##/  #######/

    TRajectory Analyzer and VISualizer  -  Open-source free software under GNU GPL v3

    Copyright (c) Martin Brehm      (2009-2022), University of Halle (Saale)
                  Martin Thomas     (2012-2022)
                  Sascha Gehrke     (2016-2022), University of Bonn
                  Barbara Kirchner  (2009-2022), University of Bonn

    http://www.travis-analyzer.de

    Please cite: J. Chem. Phys. 2020, 152 (16), 164105.         (DOI 10.1063/5.0005078 )
                 J. Chem. Inf. Model. 2011, 51 (8), 2007-2023.  (DOI 10.1021/ci200217w )

    There is absolutely no warranty on any results obtained from TRAVIS.

 #  Running on LAPTOP-V7PSSN9N at Sun May 11 22:17:52 2025 (PID 998)
 #  Running in /home/armvo/AtabekIsm/workspace/projects/lab04
 #  Version: Jul 29 2022, built at Jan 14 2023, 12:32:45, compiler "12.2.0", GCC 12.2.0
 #  Target platform: Linux, __cplusplus=201703L, Compile flags: NEW_CHARGEVAR DEBUG_ARRAYS
 #  Compiled with OpenMP, but USE_OMP not switched on in "config.h"!
 #  Machine: x86_64, char=1b, int=4b, long=8b, addr=8b, 0xA0B0C0D0=D0,C0,B0,A0.
 #  Home: /home/armvo,  Executable: /usr/bin/travis
 #  Input from terminal,  Output to terminal

    >>> Please use a color scheme with dark background or specify "-nocolor"! <<<

    Loading configuration from /home/armvo/.travis.conf ...

[Renaming existing File input.txt to #3#input.txt ...OK.]
Unknown parameter: "lint".

    List of supported command line options:

      -p <file>       Load position data from specified trajectory file.
                      Format may be *.xyz, *.pdb, *.lmp (LAMMPS), HISTORY (DLPOLY), POSCAR/XDATCAR (VASP),
                                    *.gro, *.dcd, or *.prmtop/*.mdcrd (Amber).
                      The bqb format (*.bqb, *.btr, *.emp, *.blist) as well as *.voronoi are also supported.
      -vel <file>     Read atom velocities from a file in addition to the position trajectory.
                      Currently, only .xyz format is supported for velocity data.
      -i <file>       Read input from specified text file.
      -c <file>       Read and execute control file (experimental).
      cubetool        Execute the CubeTool for modifying Gaussian Cube files.
      -sankey <file>  Create Sankey diagrams (file name is optional).
      -ramanfrompola  Compute Raman spectra from existing polarizability time series.
      (de-)compress   Start built-in bqbtool (compress trajectories to BQB format).
      check           Check BQB file integrity.

      -config <file>  Load the specified configuration file.
      -stream         Treat input trajectory as a stream (e.g. named pipe): No fseek, etc.
      -showconf       Show a tree structure of the configuration file.
      -writeconf      Write the default configuration file, including all defines values.

      -verbose        Show detailed information about what's going on.
      -nocolor        Execute TRAVIS in monochrome mode (suitable for white background).
      -dimcolor       Use dim instead of bright colors.

      -credits        Display a list of persons who contributed to TRAVIS.
      -help, -?       Shows this help.

    If only one argument is specified, it is assumed to be the name of a trajectory file.
    If no argument is specified at all, TRAVIS asks for the trajectory file to open.

    Note: To show a list of all persons who contributed to TRAVIS,
          please add "-credits" to your command line arguments, or set the
          variable "SHOWCREDITS" to "TRUE" in your travis.conf file.

    Source code from other projects used in TRAVIS:
      - lmfit     from Joachim Wuttke
      - kiss_fft  from Mark Borgerding
      - voro++    from Chris Rycroft

    http://www.travis-analyzer.de

    Please cite all of the following articles for the analyses you have used:

  * For TRAVIS in general:

    "TRAVIS - A Free Analyzer for Trajectories from Molecular Simulation",
    M. Brehm, M. Thomas, S. Gehrke, B. Kirchner; J. Chem. Phys. 2020, 152 (16), 164105.   (DOI 10.1063/5.0005078 )

    "TRAVIS - A Free Analyzer and Visualizer for Monte Carlo and Molecular Dynamics Trajectories",
    M. Brehm, B. Kirchner; J. Chem. Inf. Model. 2011, 51 (8), pp 2007-2023.   (DOI 10.1021/ci200217w )

*** The End ***

armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ ex -sc '1i|<фрагмент_вставки_значка>' -cx README.md
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git add .travis.yml
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git add README.md
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git commit -m"added CI"
[main 84f03b9] added CI
 2 files changed, 13 insertions(+)
 create mode 100644 .travis.yml
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git push origin master
error: src refspec master does not match any
error: failed to push some refs to 'https://github.com/AtabekIsm/lab04'
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git push origin main
Username for 'https://github.com': AtabekIsm
Password for 'https://AtabekIsm@github.com':
To https://github.com/AtabekIsm/lab04
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/AtabekIsm/lab04'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git pull
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 1.43 KiB | 489.00 KiB/s, done.
From https://github.com/AtabekIsm/lab04
 * [new branch]      main       -> origin/main
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> main

armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git pull origin master
fatal: couldn't find remote ref master
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git pull origin main
From https://github.com/AtabekIsm/lab04
 * branch            main       -> FETCH_HEAD
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint:
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint:
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
fatal: Need to specify how to reconcile divergent branches.
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ git push origin main
Username for 'https://github.com': AtabekIsm
Password for 'https://AtabekIsm@github.com':
To https://github.com/AtabekIsm/lab04
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'https://github.com/AtabekIsm/lab04'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. If you want to integrate the remote changes,
hint: use 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/projects/lab04$ popd
~/AtabekIsm/workspace
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ export LAB_NUMBER=04
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
Cloning into 'tasks/lab04'...
remote: Enumerating objects: 84, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 84 (delta 0), reused 0 (delta 0), pack-reused 81 (from 1)
Receiving objects: 100% (84/84), 2.11 MiB | 28.00 KiB/s, done.
Resolving deltas: 100% (23/23), done.
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ mkdir reports/lab${LAB_NUMBER}
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace$ cd reports/lab${LAB_NUMBER}
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/reports/lab04$ edit REPORT.md
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/reports/lab04$ gist REPORT.md
gist: (WARNING) fread failed (command) on CGM file REPORT.md
gist: (WARNING) BEGIN METAFILE element missing
gist: (WARNING) REPORT.md is not a binary CGM, cannot open
gist> ^C
armvo@LAPTOP-V7PSSN9N:~/AtabekIsm/workspace/reports/lab04$
