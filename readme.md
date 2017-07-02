# dpg - Deterministic Password Generator

dpg is a deterministic password generator that does not store data or keep state. Its output is based purely on user input.

## To Build C++ executable

```bash
$ cd c++ && make
```

## To Build Java jar

```bash
$ cd java && ./build.sh
```

## To Run Python, Java or C++ version

```bash
$ python dpg.py
$ java -jar dpg.jar
$ dpg "The sentence" word
```

## Usage Recommendations

  * Use the same sentence everywhere. Commit it to memory.
  * Use a different word for different sites. Be consistent with case (e.g. google, facebook, twitter, etc.)
  * If you need to change all of your passwords, change the sentence.
  * If you need to change one site password, change the word.

## Some background

I wrote DPG because I sometimes work in highly audited/regulated environments and I needed a way to recall dozens of complex passwords that change frequently and I disagree with the core concepts of most traditional password management software in use today. I believe a few of these programs are OK and I've used several of them and encouraged others to do so, but after trying to make traditional password managers work for several years, I gave up and decided that their approach is fundamentally flawed.

And by the way, if after reading this you still wish to use a traditional password manager, I suggest that you put your passwords into a plain text file and symmetrically encrypt it with [GPG](https://www.gnupg.org/) or use [Password Safe](https://pwsafe.org/). I have no relationship with either project.

OK, onto my argument. I disagree with two common concepts used by traditional 
password managers:

  * Password Storage
  * Web & Browser Integration

When passwords are stored, they must be encrypted and then retrieved later when needed. Storage, of any type, is a burden. Users are required to backup stored passwords and synchronize them across multiple devices and implement measures to protect the stored passwords or at least log access to the stored passwords for audit purposes. Also, unless backups occur regularly, if the encrypted password file becomes corrupt, lost or just stops working, then all the passwords are lost and must be manually reset.

Users must also devise a "master password" to retrieve the encrypted passwords stored by the password management software. This "master password" is a weak point. If the "master password" is exposed, or there is a slight possibility of potential exposure, confidence in the passwords are lost immediately.

My other concern with password storage is proper encryption. Are you sure the encryption used to store the passwords is implemented correctly? Has the encryption been externally validated? Some password management software is closed-source and proprietary and cannot be verified or validated in any way. Encryption is hard. Even expert developers with many years of experience make mistakes that render encryption weak or in some cases almost useless. Even open-source, peer reviewed code, written and reviewed by well-respected experts may have subtle bugs when it comes to encryption.

Now, for my second disagreement with traditional password managers. I believe that password management should only occur locally on end use devices, not on remote servers (aka "in the cloud") and not in the client web browser.

Remote servers are outside the user's control and thus cannot be trusted with password management. These remote servers may not be available when needed and may not be storing or transmitting passwords correctly. Externally, the servers may seem correct (https, etc.) but behind the scenes, no one really knows what's going on, how the passwords are being transmitted, generated, stored, or who has access to them. 

Web browsers today have "everything but the kitchen sink" capabilities built-in and are becoming more and more complex each year. They are turning into whole platforms that have browser plug-ins and extensions for every possible need known to mankind. While many of these add-ons are handy and useful, I do not trust these add-ons with password management. Browsers are just too complex and have far too much going on to trust them with password management. In short, browsers have no place in secure password management.

For the reasons listed above, I believe that the concepts of traditional password management software are fundamentally flawed and thus should not be a consideration when deciding on a secure password management solution.

DPG addresses these flaws and allows users to have strong, memorable passwords (with measurable bit strength) that change frequently.

DPG does not store passwords, it only generates passwords when needed. Because of this, the need to backup, synchronize and properly encrypt passwords is entirely removed. This also eliminates the weak point of having a "master password" that immediately unlocks all of the other passwords. There is nothing to audit access to and nothing to become lost, stolen or corrupt either. No storage means you have none of the problems associated with traditional password management storage.

Also, DPG only runs locally on end-use devices. It is a stand-alone application that does not rely on remote servers, or "the cloud", and it is not integrated into web browsers along with the numerous other browser "add-ons". DPG is also fully open-source and the passwords it generates can be verified and validated by other external programs.

In conclusion, password managers are important, but they shouldn't be difficult to deal with or untrustworthy. DPG removes many of the traditional pain points and trust issues that I have experienced with traditional password management software. I hope you find it as useful as I do.

## Notes

DPG is based on my earlier work SHA1_Pass.

