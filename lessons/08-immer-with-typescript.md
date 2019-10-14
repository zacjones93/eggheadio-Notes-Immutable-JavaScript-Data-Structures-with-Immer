## 12. [Type Immutable Immer Data with TypeScript](https://egghead.io/lessons/react-type-immutable-immer-data-with-typescript)

**Because the code put in recipe functions is plain, native, mutable JavaScript code, Immer is naturally suited to be used in conjunction of TypeScript (or Flow).**

Immer is just functions updating objects, nothing fancy so TypeScript *Just Works* by defining  the objects.

e.g.

    interface Gift {
      readonly id: string
      readonly description: string
      readonly image: string
      readonly reservedBy?: number
    }

**You will get compile errors on all you your recipe functions if you type everything with `readonly` (you should).** This makes sense because recipes are mutable even though the data they refer to is immutable.

Immer provides a utility that will let your recipes be mutable.

e.g.

    export const addGift = produce((draft: Draft<State>, id: string, description: string, image: string) => {
      draft.gifts.push({
        id,
        description,
        image,
        reservedBy: undefined
      })
    })

[<- prev](https://github.com/zacjones93/Community-Notes-Immutable-JavaScript-Data-Structures-with-Immer/blob/master/lessons/07-write-asynchronous-producers-in-immer-and-why-you-shouldn-t.md) [next ->](https://github.com/zacjones93/Community-Notes-Immutable-JavaScript-Data-Structures-with-Immer/blob/master/lessons/09-update-immutable-state-with-react-usereducer-through-immer.md)
