# Two Sum

Dada uma matriz de inteiros e um valor alvo inteiro, retorne os indices de dois números que quando somados, resulte no mesmo valor que o alvo.

Utilizando uma estrutura de dados, hashmap ou dicionário
1. Percorremos cada elemento da matriz
2. Pegamos o elemento alvo e subtraimos com o elemento contido na matriz, resultando no resto
3. Com o resto, inserimos na estrutura de dados
4. Pegamos o próximo elemento da matriz, e verificamos se existe esse valor no hashmap

Utilizamos o hashpmap para armazenar o resto:

Matriz: [1,2,3,4]
Alvo: 3

resto = 3 - 1, resultado é 2
Adicionamos ao hashmap


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