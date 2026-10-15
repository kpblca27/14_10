//1 уникальность
function getUnique(arr) {
    const uniqueArr = [];
    for (let i = 0; i < arr.length; i++) {
        if (uniqueArr.indexOf(arr[i]) === -1) {
            uniqueArr.push(arr[i]);
        }
    }
    return uniqueArr;
}
console.log(getUnique([6, 7, 6, 7, 67, 670, 1])); 

//2 фильтр (+)
function getPositive(arr) {
    let positiveArr = [];
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] > 0) {
            positiveArr.push(arr[i]);
        }
    }
    return positiveArr;
}

//3 сумма и ср.знач
function getSumAndAverage(arr) {
    if (arr.length === 0) return { sum: 0, average: 0 };
    let sum = 0;
    for (let i = 0; i < arr.length; i++) {
        sum += arr[i];
    }
    let average = sum / arr.length;
    return { sum: sum, average: average };
}
console.log(getSumAndAverage([145, 27, 367, 9, 3])); 

//4 максимум
function getMaxOfThree(a, b, c) {
    let max = a;
    if (b > max) { max = b; }
    if (c > max) { max = c; }
    return max;
}

//5 четнечет
function checkEven(num) {
    if (num % 2 === 0) {
        return "четное";
    } else {
        return "нечетное";
    }
}
console.log(checkEven(67), "и", checkEven(6));

//6 подсчет тлов
function countWords(str){
    let words = str.toLowerCase().match(/[а-яёa-z0-9]+/g);
    let counts = {};
    if (!words) return counts;
    for (let i = 0; i < words.length; i++) {
        let word = words[i];
        if (counts[word]) {
            counts[word]++;
        } else {
            counts[word] = 1;
        }
    }
    return counts;
}
console.log(countWords("привет мир привет всем"));

//7 второе по велич.уникальное слово
function getSecondLargest(arr) {
    let unique = [];
    for (let i = 0; i < arr.length; i++) {
        if (unique.indexOf(arr[i]) === -1) {
            unique.push(arr[i]);
        }
    }
    if (unique.length < 2) return null;
    unique.sort(function(a, b) { return b - a; });
    return unique[1];
}
console.log(getSecondLargest([6, 67, 10, 2, 6]));

//8 ср.балл
function getAverageScore(scores) {
    if (scores.length === 0) return 0;
    let sum = 0;
    for (let i = 0; i < scores.length; i++) {
        sum += scores[i];
    }
    return sum / scores.length;
}
console.log("средний балл:", getAverageScore([4, 5, 3, 5, 4]));

// 9 ру-ин
function transliterate(str) {
    let map = {
        'а':'a', 'б':'b', 'в':'v', 'г':'g', 'д':'d', 'е':'e', 'ё':'yo', 'ж':'zh',
        'з':'z', 'и':'i', 'й':'y', 'к':'k', 'л':'l', 'м':'m', 'н':'n', 'о':'o',
        'п':'p', 'р':'r', 'с':'s', 'т':'t', 'у':'u', 'ф':'f', 'х':'h', 'ц':'ts',
        'ч':'ch', 'ш':'sh', 'щ':'shch', 'ъ':'', 'ы':'y', 'ь':'', 'э':'e', 'ю':'yu', 'я':'ya'
    };
    let result = "";
    let lower = str.toLowerCase();
    for (let i = 0; i < lower.length; i++) {
        let char = lower[i];
        if (map[char] !== undefined) {
            result += map[char];
        } else {
            result += char;
        }
    }
    return result;
}
console.log(transliterate("любой текст для проверки"));

//10 ф и.о
function shortenFullName(fullName) {
    let parts = fullName.trim().split(" ");
    if (parts.length < 3) return fullName;
    let surname = parts[0]; 
    let nameInitial = parts[1][0].toUpperCase() + ".";
    let patronymicInitial = parts[2][0].toUpperCase() + ".";
    return surname + " " + nameInitial + " " + patronymicInitial;
}
console.log(shortenFullName("Воробьева Регина Сергеевна")); 

//11 возраст
function groupByAge(people) {
    let groups = { young: [], adult: [], senior: [] };
    for (let i = 0; i < people.length; i++) {
        let p = people[i];
        if (p.age < 18) {
            groups.young.push(p);
        } else if (p.age <= 60) {
            groups.adult.push(p);
        } else {
            groups.senior.push(p);
        }
    }
    return groups;
}
const testPeople = [
    { name: "Гермес", age: 27 },
    { name: "Арсений", age: 30 },
    { name: "Франсуа", age: 9 },
    { name: "Уродецхз", age: 1},
    { name: "Тео", age: 89 }
];
console.log(groupByAge(testPeople));

//12 ген.пароль
function generatePassword(length) {
    let chars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%^&*";
    let password = ""; 
    for (let i = 0; i < length; i++) {
        let randomIndex = Math.floor(Math.random() * chars.length);
        password += chars[randomIndex];
    }
    return password;
}
console.log(generatePassword(90)); 

//13 общее масивров
function sovpadenia(arr1, arr2) {
    for (let i = 0; i < arr1.length; i++) {
        for (let j = 0; j < arr2.length; j++) {
            if (arr1[i] === arr2[j]) {
                return true; 
            }
        }
    }
    return false;
}
console.log(sovpadenia([9, 2, 67], [6, 7, 9])); 
