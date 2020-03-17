# Java-Basic-to-Advanced

### Java Utils

| Package      | Class | Description |
| ------------- | ------------- |-------------|
| org.springframework.util  | StreamUtils  | Simple utility methods for dealing with streams |

### Parallelism

    -Djava.util.concurrent.ForkJoinPool.common.parallelism=10
    
### Functional interface in Java 8

- Function

        @FunctionalInterface
        public interface Function<T, R> {
        
            R apply(T t);
        
        }
        
 - Consumer
 
        @FunctionalInterface
        public interface Consumer<T> {
        
            void accept(T t);
        
        }

### Reference 

- https://javahungry.blogspot.com/2020/02/variable-shadowing-and-variable-hiding.html
- https://www.java67.com/2015/12/top-30-oops-concept-interview-questions-answers-java.html
