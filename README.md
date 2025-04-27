# String_Equals

✅ Basic Concept

🔹 == in Java
		Compares references (memory addresses).

		Returns true if both variables point to the same object in memory.

🔹 .equals() in Java

		Compares content (values) of objects.

		String class overrides .equals() to check character-by-character equality.

🔥 Interview Questions & Answers

❓ Q1: What is the difference between == and .equals() in Java?
✅ Answer:

		== checks if two references point to the same object in memory.

		.equals() checks if two objects have the same content or value.

Example:

		String a = new String("hello");
		String b = new String("hello");

		System.out.println(a == b);      // false (different objects)
		System.out.println(a.equals(b)); // true (same content)
		
		❓ Q2: When should you use == and when should you use .equals()?
		
		✅ Answer:

		Use == for primitive types (like int, char, etc.) or to check if two references point to the same object.

		Use .equals() when you want to compare actual content of objects, like String, List, or custom objects that override .equals().

❓ Q3: Will == ever return true for two Strings with the same content?

		✅ Answer: Yes, if both strings point to the same interned object in the String Pool.

Example:

		String a = "test";
		String b = "test";
		System.out.println(a == b); // true (both point to same interned string)
		
But if you create with new:

		String a = new String("test");
		String b = new String("test");
		System.out.println(a == b); // false (different objects)
		
❓ Q4: What happens if .equals() is used on null?

✅ Answer: It throws a NullPointerException.

Example:

		String s = null;
		System.out.println(s.equals("test")); // ❌ throws NPE
		
Use this instead:


		System.out.println("test".equals(s)); // ✅ false, but safe
		
		
❓ Q5: Can you override equals() in your class?

		✅ Answer: Yes. To compare object content in your class, you should override both .equals() and .hashCode().

Example:

		@Override
		public boolean equals(Object obj) {
			if (this == obj) return true;
			if (obj == null || getClass() != obj.getClass()) return false;
			MyClass other = (MyClass) obj;
			return this.id == other.id;
		}
		
		
❓ Q6: What is String interning in Java?
✅ Answer: String interning means that Java stores only one copy of each literal string in a special memory area called the String pool.

So:

		String a = "hello";
		String b = "hello";
		System.out.println(a == b); // true (interned)



