Fie urmatoarele structuri de date:
Rescrieti structurile de date de mai jos folosind limbajul Hugo templating :
names = ["Anya", "Rares", "Georgeta", "Diana"]
user = {
    name: "Diana",
    age: 24,
    height: 1.75,
    place: "Romania" 
}

1. Itereaza prin array-ul names cu bucla "range", folosind urmatoarele metode:
- folosind contextul
- cu variabila pentru fiecare element din array
- cu variabile pentru index si valoarea elementelor din array

2. Itereaza prin map-ul "user" folosind bucla "range", cu variabile pentru chei si valorile aferente lor.
----------------------------
Rezolvare: 

 {{ $names:= slice "Anya" "Rares" "Georgeta" "Diana" }}

        {{ range $names }}
         {{ . }}
        {{ end }} <br>

        {{ range $name:= $names }}
           {{ $name}}
        {{ end }} <br>

        {{ range $index, $name:= $names}}
            <p>{{ $name }} se afla pe pozitia {{ $index }} </p>
        {{ end }} <br>

        {{ $user:= dict 
            "name" "Diana"
            "age" 24
            "height" 1.75
            "place" "Romania"
        }}

        {{ range $cheie, $date:= $user }}
            {{ $cheie}}  {{ $date }}
            <p>Her {{ $cheie}} is {{ $date }}</p>
        {{ end }} <br><br>

        <p>Her name is {{$user.name}}, she is {{$user.age}}, she is {{$user.height}} meters heigh, and she lives in {{ $user.place}}. </p>

        <br><br>
