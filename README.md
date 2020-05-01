# Indepre
infectious disease prediction model. SIR model, SEIR model and more

# Code
```js
function idpSIR(s, i, r, eons, rateSI, rateIR) {
	var n = s+i+r;

	var Susceptible = [s];
	var Infected = [i];
	var Resistant = [r];
	for (let i = 0; i < eons; i++) {
        var stoi = (rateSI*Susceptible[i]*Infected[i])/n;
        var itor = Infected[i] * rateIR;
        Susceptible.push(Susceptible[i] -stoi);
        Infected.push(Math.floor(Infected[i] + stoi - itor));
        Resistant.push(Resistant[i] + itor);


	}
	return [Susceptible, Infected, Resistant];
}
```
