# Chaining-optionals-with-map-and-flatMap

// Using map() and flatMap() on optionals you can chain multiple operations without having to use lengthy if lets or guards:

var myURL: String? = "https://www.naver.com/"

func handle(_ url: URL) {
    print("handle: \(url)")
}

// BEFORE
guard let url = myURL else {
    return
}

guard let url = URL(string: url) else {
    return
}
handle(url)

// AFTER
myURL
    .flatMap(URL.init)
    .map(handle)
