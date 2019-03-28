SeeBiNum - see binary number  
2019-02-14..2019-03-21  
Dwayne Robinson  
Displays a number in various formats as binary/hex or vice versa.

## Usage examples

    seebinum 3.14159
    seebinum -13
    seebinum showbinary -13
    seebinum showhex -13
    seebinum 0x4240
    seebinum 0b1101
    seebinum float16 3.14
    seebinum float16 raw 0x4240
    seebinum uint32 mul 3 2 add 3 2 subtract 3 2 dot 1 2 3 4
    seebinum float32 0x2.4p0

## Options

    showbinary showhex - display raw bits as binary or hex (default)
    showhexfloat showdecfloat - display float as hex or decimal (default)
    raw num - treat input as raw bit data or as number (default)
    add subtract multiply dot - apply operation to following numbers
    float16 bfloat16 float32 float64 uint8 uint16 uint32 uint64 int8 int16 int32 int64 - set type

## Sample output

Display pi:

    SeeBiNum.exe 3.14159
    To binary:
             uint8 3 -> 0x03
            uint16 3 -> 0x0003
            uint32 3 -> 0x00000003
            uint64 3 -> 0x0000000000000003
              int8 3 -> 0x03
             int16 3 -> 0x0003
             int32 3 -> 0x00000003
             int64 3 -> 0x0000000000000003
           float16 3.14063 -> 0x4248
          bfloat16 3.14063 -> 0x4049
           float32 3.14159 -> 0x40490FD0
           float64 3.14159 -> 0x400921F9F01B866E

    From binary:
             uint8 3 <- 0x03
            uint16 3 <- 0x0003
            uint32 3 <- 0x00000003
            uint64 3 <- 0x0000000000000003
              int8 3 <- 0x03
             int16 3 <- 0x0003
             int32 3 <- 0x00000003
             int64 3 <- 0x0000000000000003
           float16 1.78814e-07 <- 0x0003
          bfloat16 2.75506e-40 <- 0x0003
           float32 4.2039e-45 <- 0x00000003
           float64 1.4822e-323 <- 0x0000000000000003

Value 1:

    SeeBiNum.exe 1
    To binary:
             uint8 1 -> 0x01
            uint16 1 -> 0x0001
            uint32 1 -> 0x00000001
            uint64 1 -> 0x0000000000000001
              int8 1 -> 0x01
             int16 1 -> 0x0001
             int32 1 -> 0x00000001
             int64 1 -> 0x0000000000000001
           float16 1 -> 0x3C00
          bfloat16 1 -> 0x3F80
           float32 1 -> 0x3F800000
           float64 1 -> 0x3FF0000000000000

    From binary:
             uint8 1 <- 0x01
            uint16 1 <- 0x0001
            uint32 1 <- 0x00000001
            uint64 1 <- 0x0000000000000001
              int8 1 <- 0x01
             int16 1 <- 0x0001
             int32 1 <- 0x00000001
             int64 1 <- 0x0000000000000001
           float16 5.96046e-08 <- 0x0001
          bfloat16 9.18355e-41 <- 0x0001
           float32 1.4013e-45 <- 0x00000001
           float64 4.94066e-324 <- 0x0000000000000001

Display multiple values in a specific format:

    SeeBiNum.exe float64 1 3.14159 1234
          float64 1(0x3FF0000000000000)
          float64 3.14159(0x400921F9F01B866E)
          float64 1234(0x4093480000000000)

Show as binary rather than hex:

    SeeBiNum.exe float64 showbinary 1 3.14159 1234
          float64 1(0011111111110000000000000000000000000000000000000000000000000000)
          float64 3.14159(0100000000001001001000011111100111110000000110111000011001101110)
          float64 1234(0100000010010011010010000000000000000000000000000000000000000000)

Add values:

    SeeBiNum.exe float64 add 1 3.14159 1234
    Operands:
          float64 1(0x3FF0000000000000)
          float64 3.14159(0x400921F9F01B866E)
          float64 1234(0x4093480000000000)
    Result of add:
          float64 1238.14(0x40935890FCF80DC3)