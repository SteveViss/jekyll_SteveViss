---
layout: post
title:  "Code integration"
date:   2014-03-01 16:27:52
categories: jekyll update
---

Hacque adfabilitate confisus cum eadem postridie feceris, ut incognitus haerebis et repentinus, hortatore illo hesterno clientes numerando, qui sis vel unde venias diutius ambigente agnitus vero tandem et adscitus in amicitiam si te salutandi adsiduitati dederis triennio indiscretus et per tot dierum defueris tempus, reverteris ad paria perferenda, nec ubi esses interrogatus et quo tandem miser discesseris, aetatem omnem frustra in stipite conteres summittendo.

{% highlight R %}
### Niche-Food Web Model - Williams et Martinez
#### Parameters
# S = Number of trophic species
# C = Network connectance [0,0.5[

nicheFW <- function(S,C){

### Model

vec_n <- runif(S)
vec_r <- rbeta(S,1,1/(2*C)-1)*vec_n
vec_c <- runif(S,vec_r/2,vec_n)

vec_r_inf <- vec_c - vec_r/2
vec_r_sup <- vec_c + vec_r/2

out <- matrix(0, nrow=S,ncol=S)

for (y in 1:S){
		for (i in y:S){
		if(vec_n[y]>=vec_r_inf[i] & vec_n[y]<=vec_r_sup[i]) out[i,y]=1
		if(vec_n[i]>=vec_r_inf[y] & vec_n[i]<=vec_r_sup[y]) out[y,i]=1
		}
	}
	return(out)
}

Co = function(x) sum(x)/prod(dim(x))
REPL = replicate(200, Co(nicheFW(80, 0.1)))
plot(density(REPL))
summary(REPL)
{% endhighlight %}

Alii nullo quaerente vultus severitate adsimulata patrimonia sua in inmensum extollunt, cultorum ut puta feracium multiplicantes annuos fructus, quae a primo ad ultimum solem se abunde iactitant possidere, ignorantes profecto maiores suos, per quos ita magnitudo Romana porrigitur, non divitiis eluxisse sed per bella saevissima, nec opibus nec victu nec indumentorum vilitate gregariis militibus discrepantes opposita cuncta superasse virtute.
