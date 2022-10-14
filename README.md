# MVC Homework

This is the README for the starter code of the
MVC homework. The goal of this assignment is to
introduce the "separation of concerns" in an
MVC-structured application.

## Testing your homework

To test your homework, you
can use the
on-line grading service at [https://grading.656.mba](https://grading.656.mba).

## Requirements

1. Alter the application so that it responds to requests at the
   URL path `/nickname`. The response at `/nickname` should be your
   course nickname, e.g. `roudy-raccoon` or `focusing-bear`. Note
   that it is case sensitive. This part is the same as the last
   homework assignment and you can copy that code.
2. Your app must still respond at the `/` route. We will use this
   route when testing if your app is still online. Technically,
   we'll test for a "200" HTTP response status code, this is the
   normal response code for when everything goes ok. See
   [here](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
   and [this summary](https://twitter.com/stevelosh/status/372740571749572610)
   (profanity).
3. Your app must respond at `/attendees` and list the people attending
   the party. You can find these people in the `models.go` file.
4. Your app should allow "filtering" of those attendees by name.
   For example the route `/attendees?q=kyle` should only show
   Kyle Jensen attending. The search should be case insensitive
   ("Kyle" and "kyle" are equivalent).
5. Add a submit button to the form on the `/attendees` page.

## A working example

Here
is an example running online that passes all the tests: <http://mvc-app.solutions.656.mba/>.

## Tips

1. Read the starter code and try to understand what it does. As a manager
   of developers you'll often be looking at code, reviewing code, and
   talking about code. You'll less often be writing it. Indeed, code is
   written few times and read many times, generally.
1. Remember, to compile your code do something like `go build`. To run
   it, you'd type something like `./mvc` where `mvc` is the
   name of your binary/executable/program that was compiled (this can
   vary...yours is likely `mvc` because of the contents of the `go.mod` file).
   Or, you could run `go run .`. Either way.
1. The crux of this assignment is making the party attendees searchable.
   You'll do that work in the `attendeesHandler` likely, assuming you don't
   change my code too much. You'll want to look at the
   [Go net/http documentation](https://golang.org/pkg/net/http/). E.g you'll
   notice that the [Request struct](https://golang.org/pkg/net/http/#Request)
   has a [URL](https://golang.org/pkg/net/url/#URL) member that has a
   [Query method](https://golang.org/pkg/net/url/#URL.Query) that will let
   you get at the query parameters of the URL. Take a look at how I did that
   in the `loveHandler` function.
1. You'll want to read the documentation for the
   [Golang "strings" packackage](https://golang.org/pkg/strings/). Notice,
   in particular, the [Contains](https://golang.org/pkg/strings/#Contains)
   and [ToLower](https://golang.org/pkg/strings/#ToLower)
   functions.
1. Be sure to make git commits after every pieces of useful work you do.
1. It is likely that you'll want to deploy your app on Heroku or fly.io.

## Caveats

Purists will notice this isn't really MVC. It is
close to the colloquial usage of the term.
