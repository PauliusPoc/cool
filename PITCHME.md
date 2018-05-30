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

  


