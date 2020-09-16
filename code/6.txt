class Solution {
    public String convert(String s, int numRows) {
        if(numRows==1)return s;
        StringBuilder A[]=new StringBuilder[numRows];
        for(int i=0;i<A.length;i++){
            A[i]=new StringBuilder();
        }
        
        int r=0;
        boolean dir=true;
        for(int i=0;i<s.length();i++){
            A[r].append(s.charAt(i)+"");
            if(dir)r++;
            else r--;

            if(r>=numRows){
                r-=2;
                dir=false;
            }
            if(r<0){
                r+=2;
                dir=true;
            }
        }
        
        
        
        StringBuilder res=new StringBuilder();
        for(StringBuilder str:A){
            res.append(str.toString());
        }
        return res.toString();
    }
}
