# Weighted quick-union algorithm with path compression

Union Find is an algorithm that uses a disjoint-set data structure. It allows us to efficiently connect any items of a given list and to efficiently check whether two items of this list are connected (any degree of separation) or not.

Possible applications where we might want to find out whether two items are connected to each other are:
* Social networks
* Computers in a network
* Web pages on the Internet
* Transistors in a computer chip
* Pixels in a digital photo
* Metallic sites in a composite system

Click [here](https://www.cs.princeton.edu/~rs/AlgsDS07/01UnionFind.pdf) for more information.

The running time of this algorithm is linear.

This a Ruby implementation of [Robert Sedgewick](http://www.cs.princeton.edu/~rs/)'s and [Kevin Wayne](http://www.cs.princeton.edu/~wayne/contact/)'s [weighted quick-union algorithm with path compression](http://algs4.cs.princeton.edu/15uf/UF.java.html). Credit goes to these two authors of the book [Algorithms](http://www.amazon.com/gp/product/032157351X/ref=as_li_qf_sp_asin_il_tl?ie=UTF8&tag=algs4-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=032157351X) and to the many computer scientists that have contributed to this algorithm in the past decades.

## Installation

Add this line to your application's Gemfile:

    gem 'union_find'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install union_find

## Usage

1. Create a new instance of 'UnionFind' and pass in an array of items:

```ruby
union_find = UnionFind::UnionFind.new(['Grandfather', 'Father', 'Daughter', 'Single Person'])
```

2. Connect items (in any order):

```ruby
union_find.union('Grandfather', 'Father')
union_find.union('Father', 'Daughter')
```

3. Check whether to items are connected (in any order):

```ruby
union_find.connected?('Grandfather', 'Daughter')
=> true
union_find.connected?('Daughter', 'Father')
=> true
union_find.connected?('Grandfather', 'Single Person')
=> false
```

4. Check how many isolated items there are. In this example, there are 2, namely the family the family tree (Grandfather - Father - Daugther) and the Single Person:

```ruby
union_find.count_isolated_components
=> 2
```

## Contributing

1. Fork it ( https://github.com/[my-github-username]/union_find/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
