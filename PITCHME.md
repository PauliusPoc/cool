# Coolest implementations
## Augustinas Makevičius

--- 

### 3 užduotis

![Jokes](c++-c-class.jpg)

---
```c++11
void ArKietas(StrongVector<Studentas> &koleg, StrongVector<Studentas> &geek, bool arVidurkiu) {
    auto fx = RibaV;
    if (!arVidurkiu) fx = RibaM;
    auto it = std::stable_partition(koleg.begin(),koleg.end(),fx);
    auto posID = std::distance(koleg.begin(), it);
    geek.assign(koleg.begin(), it);
    koleg.erase(koleg.begin(),it);
}
```
---
```c++11
double Studentas::mediana() {
    std::sort(nDarbai_.begin(), nDarbai_.end());
    return (nDarbai_.size() % 2 == 0 ? (nDarbai_[nDarbai_.size() / 2] + nDarbai_[nDarbai_.size() / 2 - 1]) / 2
                                    : nDarbai_[nDarbai_.size() / 2]) * 0.4 + 0.6 * egzam_;
}
double Studentas::vidurkis(){
    double suma{};
    suma = accumulate(nDarbai_.begin(), nDarbai_.end(), 0.0);
    return (suma / nDarbai_.size()) * 0.4 + 0.6 * egzam_;
}
```
---

### 4 užduotis
![Jokes](image61.png)

---
```c++
void assign(std::initializer_list<T> ilist){
        alokatorius.deallocate(elem, sz);
        elem = alokatorius.allocate(ilist.size());
        std::copy(ilist.begin(),ilist.end(),elem);
        sz = ilist.size();
        cap = ilist.size();
}
template< class... Args > 
iterator emplace( size_type posID, Args&&... args ) {
        if (sz == cap) {
            if (cap == 0) cap = 1;
            else cap *= 2;
            T *new_elem = alokatorius.allocate(cap);
            std::move(elem, elem + posID, new_elem);
            alokatorius.construct(new_elem + posID, std::forward<Args>(args)...);
            std::move(elem + posID, elem + sz, new_elem + posID + 1);
            alokatorius.deallocate(elem, sz);
            elem = new_elem;
        } else {
            std::move(elem + posID, elem + sz, elem + posID + 1);
            alokatorius.construct(elem + posID, std::forward<Args>(args)...);
        }
        sz++;
        return &elem[posID];
}
```

---

![Jokes](image4.png)

---
    








