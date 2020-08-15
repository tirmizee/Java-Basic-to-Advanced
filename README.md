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

### CompletableFuture in Java 8

#### Sync
    
    public static void main(String[] args) throws InterruptedException, ExecutionException {
        CompletableFuture<String> completableFuture = new CompletableFuture<>();
        completableFuture.complete(cal());
        System.out.println(completableFuture.get());
        System.out.println("finish");
    }

    public static String cal() throws InterruptedException {
        Thread.sleep(5000L);
        return "Hello";
    }

    Result
    Hello
    finish

#### Async

	public static void main(String[] args) throws InterruptedException, ExecutionException {
		CompletableFuture<Void> completableFuture = CompletableFuture.runAsync(() -> {
			for (int i = 0; i < 5; i++) {
				System.out.println("RunAsync");
			}
			System.out.println("Complete Run Async");
		}).thenAccept(Void ->{
			System.out.println("Next Run Async");
		});
		
		System.out.println("Statement");
		
		// Block and wait for the future to complete
		completableFuture.get();
	}

### Java Inner Nested

	public class Main {

		private String name;

		public String getName() {
			return name;
		}

		public void setName(String name) {
			this.name = name;
		}
	
		class Inner {

			private String name;

			public String getName() {
				return name;
			}

			public void setName(String name) {
				this.name = name;
			}

		}
    
		static class StaticInner {

			private String name;

			public String getName() {
				return name;
			}

			public void setName(String name) {
				this.name = name;
			}

		}
	
	}
.

	public static void main(String[] args) {
		
		Main main = new Main();
		main.setName("main");
		
		Main.Inner inner = main.new Inner();
		inner.setName("inner");
		
		Main.StaticInner staticInner = new Main.StaticInner();
		staticInner.setName("staticInner");
		
	}

### Reference 

- https://javahungry.blogspot.com/2020/02/variable-shadowing-and-variable-hiding.html
- https://www.java67.com/2015/12/top-30-oops-concept-interview-questions-answers-java.html
