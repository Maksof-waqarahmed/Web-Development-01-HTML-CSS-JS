```js
const employees = [
    { name: "John", age: 30, salary: 4000, department: "HR" },
    { name: "Jane", age: 25, salary: 6000, department: "Marketing" },
    { name: "Bob", age: 35, salary: 5500, department: "IT" },
    { name: "Alice", age: 40, salary: 7000, department: "IT" },
    { name: "Mike", age: 32, salary: 4800, department: "HR" },
    { name: "Emily", age: 28, salary: 6500, department: "Marketing" },
    { name: "David", age: 45, salary: 3000, department: "IT" },
    { name: "Sarah", age: 38, salary: 7200, department: "HR" },
    { name: "Tom", age: 31, salary: 6800, department: "Marketing" },
    { name: "Lily", age: 29, salary: 6200, department: "IT" },
];

const groupedByDepartment = Object.groupBy(employees, (employee) => employee.department);
const groupedByAge = Object.groupBy(employees, ({ department }) => department);
const groupedByAge = Object.groupBy(employees, (employee) => employee.age);
const groupedBySalary5000 = Object.groupBy(employees, (employee) => {
    return employee.salary >= 5000 ? "More than 5000" : "Less than 5000";
});
console.log(groupedByDepartment); // { HR: [ ... ], Marketing: [ ... ], IT: [ ... ] }
console.log(groupedByAge); // { HR: [ ... ], Marketing: [ ... ], IT: [ ... ] }
console.log(groupedByAge); // { 25: [ ... ], 28: [ ... ], 30: [ ... ], 32: [ ... ], 35: [ ... ], 38: [ ... ], 40: [ ... ], 45: [ ... ] }
console.log(groupedBySalary5000); // { More than 5000: [ ... ], Less than 5000: [ ... ] }
```




