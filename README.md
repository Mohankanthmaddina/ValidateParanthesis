# ValidateParanthesis
# ValidateParanthesis
class Solution {
    int top=-1;
    public boolean isValid(String s) {
        char[] c=new char[s.length()];
        char previous=0;
        for(int i=0;i<s.length();i++){
          char ch=s.charAt(i);
            if(top!=-1){
              if(c[top]<42)
                previous=(char)(c[top]+1);
              else
                previous=(char)(c[top]+2);
            }
            else  previous=0;
            if(ch==previous) c[top--]=0;
            else    c[++top]=ch;
        }
        return top==-1;
    }
}
