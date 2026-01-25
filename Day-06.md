# Day 06

**Date:** 2025-01-24
**Concept:** Sliding Window: Variable size window
**Problem:** Longest Substring Without Repeating Characters
**Difficulty:** Medium
**Time Spent:** 40 minutes

## Notes
I learned about the frequency of each character which will be very easy for this problem. My program 

int lengthOfLongestSubstring(char* s) {
    int lastseen[256];
    for(int i=0;i<256;i++){
        lastseen[i]=-1;
    }
    int l=0,max=0;
 
    for(int r=0;s[r]!='\0';r++){
        char ch=s[r];
         if(lastseen[ch]>=l){
            l=lastseen[ch]+1;
         }
         lastseen[ch]=r;
         int cur=r-l+1;
          if(cur>max){
            max=cur;
          }
    }
    return max;
}
