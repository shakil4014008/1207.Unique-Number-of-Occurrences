# 1207.Unique-Number-of-Occurrences

## C#
```C#
  public bool UniqueOccurrences(int[] arr) {
            Dictionary<int, int> hs = new Dictionary<int, int>();
            List<int> list = new List<int>();
            

            for (int i = 0; i < arr.Length; i++)
            {
                if (!hs.ContainsKey(arr[i]))
                {
                    hs.Add(arr[i], 1);
                }
                else
                {                     
                    hs[arr[i]] = hs[arr[i]] + 1;
                }
            }
            
            HashSet<int> hset = new HashSet<int>();
            foreach(KeyValuePair<int, int> item in hs)
            {
                list.Add(item.Value);
            }
            hs.Clear();//to insert new set of data

            foreach(var item in list)
            {
                if (!hs.ContainsKey(item))
                {
                    hs.Add(item, 1);
                }
                else
                {
                    return false;
                }
            }


            return true;
    }
```
