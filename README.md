[![Build Status](https://travis-ci.org/pokesource/pokekotlin.svg?branch=master)](https://travis-ci.org/pokesource/pokekotlin)
[![Download](https://api.bintray.com/packages/sargunster/maven/PokeKotlin/images/download.svg) ](https://bintray.com/sargunster/maven/PokeKotlin/_latestVersion)

# PokeKotlin

Kotlin wrapper for [PokeApi](https://github.com/phalt/pokeapi). Currently under development.

## Status

Model classes: 100%

API interface: 100%

Testing: about 95%

## Example

### Kotlin

```kotlin
fun main(args: Array<String>) {
    PokeApi.getPokemon(1).promise success {
        println(it)
    } fail {
        it.printStackTrace()
    }
}
```

### Java

```java
public class Example {
    public static void main(String[] args) {
        PokeApi.INSTANCE.getPokemon(1).enqueue(new Callback<Pokemon>() {
            @Override
            public void onResponse(Call<Pokemon> call, Response<Pokemon> response) {
                System.out.println(response.body());
            }

            @Override
            public void onFailure(Call<Pokemon> call, Throwable throwable) {
                throwable.printStackTrace();
            }
        });
    }
}
```

## Download

### Gradle

```groovy
dependencies {
    compile 'me.sargunvohra.lib:PokeKotlin:<version>'
}
```

### Kobalt

```kotlin
val p = project {
    dependencies {
        compile("me.sargunvohra.lib:PokeKotlin:<version>")
    }
}
```
