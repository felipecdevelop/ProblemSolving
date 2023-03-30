# Two Sum

Dada uma matriz de inteiros e um valor alvo inteiro, retorne os indices de dois números que quando somados, resulte no mesmo valor que o alvo.


```csharp
public int[] TwoSum(int[] nums, int target) {
        var hash = new Dictionary<int, int>();

        for(int i = 0; i < nums.Length;i++){

            int resto = target - nums[i];

            if(hash.ContainsKey(nums[i])){
                return new int[]{hash[nums[i]], i};
            }

            hash.TryAdd(resto, i);

        }
        return new int[]{};
}
```