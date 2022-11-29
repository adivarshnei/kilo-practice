# Done Before [Display Keypresses](https://viewsourcecode.org/snaptoken/kilo/02.enteringRawMode.html)

Source: [https://viewsourcecode.org/snaptoken/kilo/](https://viewsourcecode.org/snaptoken/kilo/)

---
In-Built Variables Used:

<table>
<tr>
<th>Variable</th>
<th>From</th>
<th>Description</th>
</tr>
<tr>
<td>

```c
#define EAGAIN 11
```
</td>
<td><code>errno.h</code></td>
<td>Resource temporarily unavailable (may be the same value as <code>EWOULDBLOCK</code>.
</tr>
<tr>
<td>

```c
#define ECHO 0000010
```
</td>
<td><code>termios.h</code></td>
<td>Echo input characters to the terminal</td>
</tr>
<tr>
<td>

```c
#define TCSAFLUSH 2
```
</td>
<td><code>termios.h</code></td>
<td>
  The change occurs after all output written to the object referred by <code>FD</code> has been transmitted, and all input that has been received but not read will be discarded before the change is made
</td>
</tr>
<tr>
<td>

```c
#define ICANON 0000002
```
</td>
<td><code>termios.h</code></td>
<td>
  Enables canonical mode in the terminal.
</td>
</tr>
<tr>
<td>

```c
#define ISIG 0000001
```
</td>
<td><code>termios.h</code></td>
<td>
  When any of the characters <code>INTR</code> (stop current command), <code>QUIT</code> (stop current command, if <code>INTR</code> doesn't work), <code>SUSP</code> (suspend current command), or <code>DSUSP</code> (delayed suspend) are received, generate the corresponding signal.
</td>
</tr>
<tr>
<td>

```c
#define IXON 0002000
```
</td>
<td><code>termios.h</code></td>
<td>
  Enable <code>XON</code>/<code>XOFF</code> (software flow control and data transp) flow control on output.
</td>
</tr>
<tr>
<td>

```c
#define IEXTEN 0100000
```
</td>
<td><code>termios.h</code></td>
<td>
  Enable implementation-defined input processing. This flag, as well as <code>ICANON</code>) must be enabled for the special characters <code>EOL2</code>, <code>LNEXT</code>, <code>REPRINT</code>, <code>WERASE</code> to be interpreted, and for the <code>IUCLC</code> flag to be effective.
</td>
</tr>
<tr>
<td>

```c
#define ICRNL 0000400
```
</td>
<td><code>termios.h</code></td>
<td>
  Translate carriage returns to newline on input (unless <code>IGNCR</code> is set).
</td>
</tr>
<tr>
<td>

```c
#define OPOST 0000001
```
</td>
<td><code>termios.h</code></td>
<td>
  Enable implementation-defined output processing.
</td>
</tr>
<tr>
<td>

```c
#define BRKINT 0000002
```
</td>
<td><code>termios.h</code></td>
<td>
  If <code>IGNBRK</code> is set, a <code>BREAK</code> is ignored.  If it is not set but <code>BRKINT</code> is set, then a <code>BREAK</code> causes the input and output queues to be flushed, and if the terminal is the controlling terminal of a foreground process group, it will cause a <code>SIGINT</code> to be sent to this foreground process group.  When neither <code>IGNBRK</code> nor <code>BRKINT</code> are set, a <code>BREAK</code> reads as a null byte (<code>'\0'</code>), except when <code>PARMRK</code> is set, in which case it reads as the sequence <code>\377 \0 \0</code>.
</td>
</tr>
<tr>
<td>

```c
#define INPCK 0000020
```
</td>
<td><code>termios.h</code></td>
<td>
  Enable input parity checking.
</td>
</tr>
<tr>
<td>

```c
#define ISTRIP 0000040
```
</td>
<td><code>termios.h</code></td>
<td>
  Strip off eighth bit.
</td>
</tr>
<tr>
<td>

```c
#define CSIZE 0000060
```
</td>
<td><code>termios.h</code></td>
<td>
  Character size mask. Values are <code>CS5</code>, <code>CS6</code>, <code>CS7</code>, or <code>CS8</code>.
</td>
</tr>
<tr>
<td>

```c
#define VMIN 6
```
</td>
<td><code>termios.h</code></td>
<td>
  Minimum number of characters for noncanonical read (<code>MIN</code>).
</td>
</tr>
<tr>
<td>

```c
#define VTIME 5
```
</td>
<td><code>termios.h</code></td>
<td>
  Timeout in deciseconds for noncanonical read (<code>TIME</code>).
</td>
</tr>
<tr>
<td>

```c
#define STDIN_FILENO 0
```
</td>
<td><code>unistd.h</code></td>
<td>Default standard input file descriptor</td>
</tr>
</table>

---
In-Built Structures Used:

<table>
<tr>
<th>Variable</th>
<th>From</th>
<th>Description</th>
</tr>
<tr>
<td>

```c
struct termios {
  tcflag_t c_iflag;
  tcflag_t c_oflag;
  tcflag_t c_cflag;
  tcflag_t c_lflag;
  cc_t     c_cc[NCCS];
};
```
</td>
<td><code>termios.h</code></td>
<td>
  Contains fields describing the general terminal interface. <br>
  <ul>
    <li>
      <code>c_iflag</code> describes the input modes of the terminal interface
    </li>
    <li>
      <code>c_oflag</code> describes the output modes of the terminal interface
    </li>
    <li>
      <code>c_cflag</code> describes the control modes of the terminal interface
    </li>
    <li>
      <code>c_lflag</code> describes the local modes of the terminal interface
    </li>
    <li>
      <code>c_cc</code> array defines the terminal special characters.
    </li>
  </ul>
  Default standard input file descriptor
</td>
</tr>
</table>

---
In-Built Functions Used:

<table>
<tr>
<th>Function</th>
<th>From</th>
<th>Description</th>
</tr>
<tr>
<td>

```c
#define iscntrl(c) __isctype((c), _IScntrl)
```
</td>
<td><code>ctype.h</code></td>
<td>
  Shall test whether <code>c</code> is a character of class <code>cntrl</code> in the current locale.<br>
  The <code>c</code> argument is of type <code>int</code>, the value of which the application shall ensure is a character representable as an <code>unsigned char</code> or equal to the value of the macro <code>EOF</code>. If the argument has any other value, the behaviour is undefined.<br>
  Shall return non-zero if <code>c</code> is a control character; otherwise, <code>0</code> is returned.
</td>
</tr>
<tr>
<td>

```c
extern int printf(const char *restrict FORMAT, ...)
```
</td>
<td><code>stdio.h</code></td>
<td>
  Writes output to <code>stdout</code>.<br>
  The <code>FORMAT</code> string is a character string, beginning and ending in its initial shift state, if any. The format string is composed of zero or more directives: ordinary characters (not <code>%</code>), which are copied unchanged to the output stream; and conversion specifications, each of which results in fetching zero or more subsequent arguments.
</td>
</tr>
<tr>
<td>

```c
extern void perror(const char *S)
```
</td>
<td><code>stdio.h</code></td>
<td>
  Produces a message on standard error describing the last error encountered during a call to a system or library function.<br>
  First (if <code>S</code> is not <code>NULL</code> and <code>*S</code> is not a null byte (<code>'\0'</code>)), the argument string <code>S</code> is printed, followed by a colon and a blank. Then an error message corresponding to the current value of <code>errno</code> and a new-line.
</td>
</tr>
<tr>
<td>

```c
extern int atexit(void (*FUNC)(void))
```
</td>
<td><code>stdlib.h</code></td>
<td>
  Registers the given function to be called at normal process termination, either via <code>exit()</code> or via return from the program's <code>main()</code>. Functions so registered are called in the reverse order of their registration; no arguments are passed.
</td>
</tr>
<tr>
<td>

```c
extern void exit(int STATUS)
```
</td>
<td><code>stdlib.h</code></td>
<td>
  Causes normal process termination and the least significant byte of <code>STATUS</code> (i.e., <code>STATUS</code> & <code>0xFF</code>) is returned to the parent.
</td>
</tr>
<tr>
<td>

```c
extern int tcgetattr(int FD, struct termios *TERMIOS_P)
```
</td>
<td><code>termios.h</code></td>
<td>
  Gets the parameters associated with <code>FD</code> and stores them in the <code>termios</code> structure referenced by <code>TERMIOS_P</code>. This function may be invoked from a backgroud process; however, the terminal attributes may be subsequently changed by a foreground process.
</td>
</tr>
<tr>
<td>

```c
extern int tcsetattr(int FD, int OPTIONAL_ACTIONS, const struct termios *TERMIOS_P)
```
</td>
<td><code>termios.h</code></td>
<td>
  Sets the parameters associated with the terminal from the <code>termios</code> structure referred to by <code>TERMIOS_P</code>. <code>OPTIONAL_ACTIONS</code> specifies when the changes take effect.
</td>
</tr>
<tr>
<td>

```c
extern ssize_t read(int FD, void *BUF, size_t NBYTES)
```
</td>
<td><code>unistd.h</code></td>
<td>
  Reads <code>NBYTES</code> from <code>BUF</code> from <code>FD</code>. Returns the number read, <code>-1</code> for errors or <code>0</code> for <code>EOF</code>. This function is a cancellation point and therefore not marked with <code>__THROW</code>.
</td>
</tr>
</table>

---
Global:

<table>
<tr>
<th>Code</th>
<th>Description</th>
</tr>
<tr>
<td>

```c
struct termios orig_termios;
```
</td>
<td>Variable used for storing and the original terminal environment.</td>
</tr>
</table>

---
```c
void enable_raw_mode()
```
<table>
<tr>
<th>Code</th>
<th>Description</th>
</tr>
<tr>
<td>

```c
struct termios raw = orig_termios;
```
</td>
<td>Variable used for storing and manipulating the terminal environment, initially set to variable containing original terminal environment</td>
</tr>
</table>

---
```c
int main()
```

<table>
<tr>
<th>Code</th>
<th>Description</th>
</tr>
<tr>
<td>

```c
char c = '\0';
```
</td>
<td>Variable input is read into, initially set as null</td>
</tr>
<tr>
<td>

```c
errno != EAGAIN;
```
</td>
<td>Checks for failure of read</td>
</tr>
<tr>
<td>

```c
c == 'q'
```
</td>
<td>Checks if entered character is <code>q</code>.</td>
</tr>
</table>
