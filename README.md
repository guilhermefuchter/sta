# sta


desafio 1 

import { Expect, ExpectExtends } from "./types/validateTypes";


interface IFullUser extends IUserWorker, IUserStudent {}


type casosDeValidacao = [
  Expect<ExpectExtends<IUserWorker, IFullUser>>, // Confere se IFullUser possui campos do Worker
  Expect<ExpectExtends<IUserStudent, IFullUser>>, // Confere se IFullUser possui campos do Student
]


interface IUserWorker {
  name: string
  work: string
}

interface IUserStudent {
  name: string
  age: number
}



desadio 2 

import { Equal, Expect } from "./types/validateTypes";


interface IExtendedUser { // Não mexa nessa interface
  siblings: number
  rating: number
  applications: string[]
}

interface ISiblingsUser { // Não mexa nessa interface
  siblings: number
}


type IExtendedWithoutFields = Omit<IExtendedUser, 'rating' | 'applications'>;


type casosDeValidacao = [
  Expect<Equal<ISiblingsUser, IExtendedWithoutFields>>, // Compara IFullUser ao Extendes com suas exceções
]


desafio 3 

import { Equal, Expect } from "./types/validateTypes";


type myFunction = (value: number) => number;


type casosDeValidacao = [
  Expect<Equal<typeof duplicarNumero, myFunction>> // Compara os tipos das funções
]


function duplicarNumero(value: number) {
  return value * 2
}


desafio 4 

import { Equal, Expect } from "./types/validateTypes";


type listType = number | string;


const list_of_packs: listType[] = []
list_of_packs.push('um')
list_of_packs.push(2)
list_of_packs.push(2.5)


desafio 5

import { Equal, Expect } from "./types/validateTypes";


interface IUserYouMade {
  name: string;
  age: number;
  work: string;
  siblings: number;
  rating: number;
  applications: string[];
  active: boolean;
}


let userYouMade: IUserYouMade;

userYouMade.name = "Nome Do Usuário";
userYouMade.age = 22;
userYouMade.work = "Analista";
userYouMade.siblings = 0;
userYouMade.rating = 10;
userYouMade.applications = ['RH', 'Dev'];
userYouMade.active = true;



