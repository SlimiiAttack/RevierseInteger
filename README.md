# RevierseInteger
//Get the reverse value of an int "-123" --> "-321"
class Solution {
public:
    int reverse(int x) 
    {
        bool Negative = false;
        int LengthOfX; std::to_string(x).length();
        std::string ReverseInt="";
        
        if (x == -2147483648)
        {
            x = 0;
        }else if (x < 0) 
        {
            Negative = true;
            x *= -1;
        } 
        // getting the length after we remove the negative sign
        LengthOfX= std::to_string(x).length();
        //
        if (((LengthOfX == 10) && ((x % 10) > 2)) || ((LengthOfX== 10)  && (x % 1000000000 > 463847412)))
        {
                x = 0;
        }
        if (x>9)
        {           
            for (int i = 1; i <= LengthOfX ; i++) 
            {             
                ReverseInt += std::to_string(x % 10);
                x /= 10;
            }
            x = std::stoi(ReverseInt);
        }

       
        if (Negative)
        {
            return x * -1;
        }else
        {
            return x;
        }

    }
};
