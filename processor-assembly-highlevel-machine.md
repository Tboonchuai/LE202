# 1.RICS-V
Processor: RICS-V

Hight level language: C
    
    int square(int num) 
    {
    return num * num;
    }
Assembly: RICS-V rv32gc clang 9.0.0
      
    square:                                 # @square
        addi    sp, sp, -16
        sw      ra, 12(sp)
        sw      s0, 8(sp)
        addi    s0, sp, 16
        sw      a0, -12(s0)
        lw      a0, -12(s0)
        mul     a0, a0, a0
        lw      s0, 8(sp)
        lw      ra, 12(sp)
        addi    sp, sp, 16
        ret
    
machine language:



---
# 2.x86

Processor: x86

Hight level language: C++

    int square(int num) {
    return num * num;
    }

Assembly: x86-64 gcc (contract labels)

      square(int):
              push    rbp
              mov     rbp, rsp
              mov     DWORD PTR [rbp-4], edi
              mov     eax, DWORD PTR [rbp-4]
              imul    eax, eax
              pop     rbp
              ret

Machine language:
