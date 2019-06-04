# CertKatz

----

CertKatz is a clone of [@harmj0y](https://twitter.com/harmj0y)'s
SafetyKatz project, slightly modified to expose [@gentilkiwi](https://twitter.com/gentilkiwi)'s [Mimikatz](https://github.com/gentilkiwi/mimikatz/) Crypto module instead of automatically dump LSASS. 

The PE loading function was slightly changed to include more of Casey Smith's POC in order to allow us to load the Mimikatz PowerShell DLL and pass commands into it. Mimikatz was modified to a slimmed down version that only has the Crypto module.


CertKatz allows you to run more than one command from the Mimikatz crypto module from the same process context. This is useful in environments where each run of a utility occurs in an independent process (cobalt strike).


CertKatz is licensed under the BSD 3-Clause license.
CertKatz was written by [@doughsec](https://twitter.com/doughsec), though I barely did anything :)

## Usage

    C:\Temp>CertKatz.exe

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

CertKatz can also be passed command line parameters. This is useful if you are running as SYSTEM and need to dump certificates in a particular user's personal store. Be careful with quoting and escaping!

## Compile Instructions

I am not planning on releasing binaries for CertKatz, so you will have to compile yourself :)

CertKatz has been built against.NET 3.5 and is compatible with[Visual Studio 2015 Community Edition](https://go.microsoft.com/fwlink/?LinkId=532606&clcid=0x409). Simply open up the project .sln, choose "release", and build.

