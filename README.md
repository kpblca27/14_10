//1
function uniqArr(arr){
const (let i = 0; i<arr.lenght; i++) {
if (uniqArr.indexOf(arr[i])===-1) {
uniqArr.push(arr[i]);
 }
  }
return uniqArr;
}

//2
function getPozitive(arr) {
const pozitiv = [];
for (let i = 0; i<arr.lenght; i++) {
if (arr[i] > 0) {
positive.push(arr[i]};
}
}
return pozitiv;
}

//3 
function getSumAndAverage(arr) {
if (arr.lenght ===0) return { sum: 0, average: 0};
let sum = 0;
for (let i=0; i<arr.lenght;i++) {
sum+= arr[i];
}
var average = sum/arr.lenght;
return {sum: sum, average: average};
}
