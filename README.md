# rk2
#include<iostream>
#include<bitset>
#include<string>
#include<algorithm>


std::stringbinarySum(conststd::string&a, conststd::string&b) {
    std::stringresult;
    intcarry=0;
    
    intlength=std::max(a.size(), b.size());
    std::stringaPadded=std::string(length-a.size(), '0') +a;
    std::stringbPadded=std::string(length-b.size(), '0') +b;


   
    for(inti=length-1; i>=0; --i) {
        intsum=(aPadded[i]-'0') +(bPadded[i]-'0') +carry;
        result.push_back((sum%2) +'0');
        carry=sum/2;
    }
    
    
    if(carry) {
        result.push_back(carry+'0');
    }



    std::reverse(result.begin(), result.end());
    
    returnresult;
}


intmain() {
    std::stringA="101101";
    std::stringB="110011";



    std::bitset<6>aBitset(A);
    std::bitset<6>bBitset(B);
    std::bitset<6>andResult=aBitset&bBitset;


 
    std::cout<<"Побитовая операция AND: "<<andResult<<std::endl;


    std::stringsumResult=binarySum(A, B);



    std::cout<<"Сумма чисел A и B: "<<sumResult<<std::endl;


    return0;
}
