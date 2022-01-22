A std::string knows its length, which makes many operations quicker.

For example, given:

const char* c1 = "Hello, world!";
const char* c2 = "Hello, world plus dog!";
std::string s1 = c1;
std::string s2 = c2;
strlen(c1) is slower than s1.length(). For comparisons, strcmp(c1, c2) has to compare several characters to determine the strings are not equal, but s1 == s2 can tell the lengths are not the same and return false immediately.

Other operations also benefit from knowing the length in advance, e.g. strcat(buf, c1) has to find the null terminator in buf to find where to append data, but s1 += s2 knows the length of s1 already and can append the new characters at the right place immediately.

When it comes to memory management, std::string allocates additional space every time it grows, which means future append operations don't need to reallocate.

