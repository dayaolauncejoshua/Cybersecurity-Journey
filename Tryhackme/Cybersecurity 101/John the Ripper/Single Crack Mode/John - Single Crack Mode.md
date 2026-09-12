**John's Single Crack mode**
    - generates password guesses based on information about the target, such as their username and GECOS information.

**Word Mangling**
    - taking known words and creating variantions of it.
    - Eg. If the username is Markus:
        - John might generate:
            Markus1
            Markus123
            MArkus
            MARKus
            Markus!
            Markus$
    - This works because some users tend to create their passwords based on their usernames, names, or other personal information

**GECOS**
    - On Linux, the /etc/passwd file contains a GECOS field (the fifth field).
    - It can contain information such as Full name, office information, phone number, other user information.
    - John can use information from this field, along with the username/home directory, to generate additional password guesses.

**Using Single Crack Mode**
    - Syntax: john --single --format=[format] [file]
    - Example: john --single --format=raw-sha256 hashes.txt
    - **Important:** Username Must Be Included
    - Single Crack needs the username associated with the hash so John knows what information to use for generating guesses.
    - Instead of 1efee03cdcb96d90ad48ccc7b8666033, Use mike:1efee03cdcb96d90ad48ccc7b8666033
    - The format is: username:hash
    - John can then use mike and other available user information to generate password variations.

**Key take:**
    - Wordlist mode → tries passwords from a wordlist.
    - Single Crack mode → intelligently generates password guesses from information about the target user.