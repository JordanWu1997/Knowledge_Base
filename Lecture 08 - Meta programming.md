# Missing Semester - Lecture 08 - Metaprogramming
- [Course_youtube_link](https://www.youtube.com/watch?v=_Ms1Z4xfqv4)
- [Course_webpage_resources](https://missing.csail.mit.edu/2020/metaprogramming/)

## Table of content
* [Missing Semester - Lecture 08 - Metaprogramming](#missing-semester---lecture-08---metaprogramming)
   * [Table of content](#table-of-content)
   * [Context](#context)
      * [Build system](#build-system)
      * [Testing](#testing)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)
## Context

### Build system
- Make
    - Find Makefile in current directory
- Makefile
    - Set pipeline target to build
    - Set rule for build process
- Repository
    - Collection of programs
        - e.g. PYPI for python
- Version of programs
    - Semantic version naming style
        - Program version naming: major.minor.patch
            - Major: API changed and not backward compatible
                - e.g. python2 v.s. python3
            - Minor: API changed but backward compatible
            - Patch: API not changed but some bugs are fixed
    - Lockfile
        - Core dependency of program
### Testing
- Unit test
    - Test specific feature
- Integration test
    - Check if features work together
- Regression test
    - Test particular pattern that caused bugs before for preventing bugs for the future
- Mocking test
    - Fake implementation to avoid testing unrelated functionality
        - e.g. Mocking network connection or mocking disk
