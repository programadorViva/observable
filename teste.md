//PROMISSE
getArticles(){
    return this.http.get('api/v1/articles')
    .then((res) => console.log(res))
    .catch((res) => console.log(res))
}
//OBSERVABLE
getArticles(){
    return this.http.get('api/v1/articles')
    .subscribe(
        res => console.log(res),
        err => console.log(res)
    )
}

//OBSERVABLE - pegando uma promise
getArticles(){
    return this.http.get('api/v1/articles')
    .toPromise()
    .then((res) => console.log(res))
    .catch((res) => console.log(res))
}

//OBSERVABLE - Retry executa 3x
getArticles(){
    return this.http.get('api/v1/articles')
    retry(3)
    .subscribe(
        res => console.log(res),
        err => console.log(res)
    )
}

//OBSERVABLE - executa até retornar erro ou retornar observable
getArticles(){
    return this.http.get('api/v1/articles')
    retryWhen(function() {

    })
    .subscribe(
        res => console.log(res),
        err => console.log(res)
    )
}