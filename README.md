This little addon is based on Google's own language detector in chrome.

It wraps this library http://code.google.com/p/chromium-compact-language-detector/

See the example.

Note that the binaries and headers linked in the Project.xcconfig.


To compile the library from the above source for your platform, you might try something like this:

```
./autogen.sh
./configure CFLAGS=-m32 CXXFLAGS=-m32 --enable-static=yes --prefix="<THE PATH TO>"/ofxLanguageDetector/libs/cld"
make
make install
```
For osx/linux (and maybe even windows), you may also need to add:

```
#define CLD_WINDOWS 1
```
to this file:

https://github.com/bakercp/ofxLanguageDetector/blob/master/libs/cld/include/encodings/compact_lang_det/win/cld_utf8statetable.h#L8

before or after you install so it doesn't pick up the windows references.

More discussion of that here:

http://code.google.com/p/chromium-compact-language-detector/issues/detail?id=1