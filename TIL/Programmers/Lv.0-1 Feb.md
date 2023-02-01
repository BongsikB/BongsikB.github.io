## <p align="center">📚 최댓값과 최솟값 </p>

```jsx
문자열 s에는 공백으로 구분된 숫자들이 저장되어 있습니다.
str에 나타나는 숫자 중 최소값과 최대값을 찾아 이를
"(최소값) (최대값)"형태의 문자열을 반환하는 함수, solution을 완성하세요.
예를들어 s가 "1 2 3 4"라면 "1 4"를 리턴하고,
"-1 -2 -3 -4"라면 "-4 -1"을 리턴하면 됩니다.

- 제한 조건
s에는 둘 이상의 정수가 공백으로 구분되어 있습니다.
```

- 입출력 예

  | s             | return  |
  | ------------- | ------- |
  | "1 2 3 4"     | "1 4"   |
  | "-1 -2 -3 -4" | "-4 -1" |
  | "-1 -1"       | "-1 -1" |

## 🧩 My Answer

```javascript
const solution = s => {
  let num = s.split(/\s/g).map(digit => {
    return Math.floor(digit);
  });
  let min = Math.min(...num);
  let max = Math.max(...num);
  return (answer = `${min} ${max}`);
};
```

> 규식이 공부에 심취하여 굳이 써본 `/\s/g` 👩‍💻 <br> `+3` 을 받은 영광스러운 답!
> ![3점을 받았습니다! 하지만 아직 응애](https://user-images.githubusercontent.com/110847597/216099696-3c2251e7-60f6-4ce1-aebe-80784a0c9746.png)

## 🧩 줍줍 Answer

```javascript
//👏👏👏
function solution(s) {
  const arr = s.split(" ");
  return Math.min(...arr) + " " + Math.max(...arr);
}
```
