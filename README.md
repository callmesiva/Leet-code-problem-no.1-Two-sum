# Brute force method -- time complexity n(2)

       int nums[] = {2,3,4,5,6};
       int target =10;
       
       Map<Integer,Integer> cache = new HashMap<>();
       
       
      for(int i=0 ; i<nums.length-1; i++)
      {
        
       for(int j=i+1; j<nums.length; j++)
       {
         if(nums[i]+nums[j]==target)
         {
           return new int[]{i,j};
         }
       }
        
      }
      return null;
       
       
# Using hashmap to reduce time -- time complexity o(n)

       int nums[] = {2,3,4,5,6};
       int target =10;
       
       Map<Integer,Integer> cache = new HashMap<>();
       
       
      for(int i=0 ; i<nums.length; i++)
      {
        
       if(cache.containsKey(target-nums[i]))
       {
         
         return new int[]{i,cache.get(target-nums[i])};
       }
        
       cache.put(nums[i],i);  
      }
      
      return null;
