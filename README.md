# mongodb module

> Use this module to easily connect with tradersclub's mongodb.
We expose a simple wrapper around mongodb common operations so
the client can build an abstraction on this.


## Installation

Use this module on your project by adding `"github.com/tradersclub/mongodb"`
to your import statement, and the run `go get ./...` so go compiler will
fetch and install the module.


## Usage

The simplest way to use it is just connecting and making a query, here's an
example:


```{golang}
// Connect to vindi database for example, you need to supply the conn string
db, err := nosql.Connect(connString, "vindi")
if err != nil {
    panic(err)
}

// Now we can make simple queries, eg. get a bill
var bill vindi.Bill
err = db.Get("bills", map[string]interface{}{"id": 123456}, &bill)
if err != nil {
    panic(err)
}

// Now bill has the result from the query
fmt.Printf("%+v\n", bill)
```


## Meta

Created by Brian Mayer and Arthur Durant.
