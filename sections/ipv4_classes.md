# IPv4 Classes Ranges

|Address Class|RANGE                       |Default Subnet Mask   |
|-------------|----------------------------|----------------------|
|A            |0.0.0.0 to 127.255.255.255  |255.0.0.0             |
|B            |128.0.0.0 to 191.255.255.255|255.255.0.0           |
|C            |192.0.0.0 to 223.255.255.255|255.255.255.0         |
|D            |224.0.0.0 to 239.255.255.255|Reserved for multicast|
|E            |240.0.0.0 to 254.255.255.255|Experimental/Reserved |

## Notes:
`127.0.0.0/8` is reserved for loopback addresses.

## How to remember this table?

**Class A** sets the first digit to `0`, you must never change that digit:

    Bin: (0)0000000 to (0)11111111
    Dec: 0 to 127

**Class B** sets the first two digits to `10`, you must never change those two digits:

    Bin: (10)000000 to (10)111111
    Dec: 128 to 191

**Class C** sets the first three digits to `110`, you must never change those three digits:

    Bin: (110)00000 to (110)11111
    Dec: 192 to 223

**Class D** sets the first four digits to `1110`, you must never change those four digits:

    Bin: (1110)0000 to (1110)1111
    Dec: 224 to 239

**Class C** sets the first five digits to `11110`, you must never change those five digits:

    Bin: (11111)000 to (11111)111
    Dec: 240 to 247