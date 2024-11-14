import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Put text here: ");
        String text = sc.nextLine();

        Map<String, Integer> wordCount = getStringIntegerMap(text);


        wordCount.entrySet()
                .stream()
                .sorted((entry1, entry2) -> entry2.getValue().compareTo(entry1.getValue()))
                .forEach(entry -> System.out.println(entry.getKey() + ": " + entry.getValue()));
    }

    private static Map<String, Integer> getStringIntegerMap(String text) {
        List<String> exclusionList = Arrays.asList("the", "of", "to", "we", "a", "is",
                "and", "in", "our", "that", "this", "must", "not", "will", "as", "be", "now",
                "come", "have", "from", "i", "with", "are", "by", "s", "for", "it", "but", "an",
                "on", "has, ", "at", "can", "so", "let");

        // Normalize the text by converting to lowercase and splitting into words
        String[] words = text.toLowerCase().split("\\W+");

        // Create a map to store the word count
        Map<String, Integer> wordCount = new HashMap<>();

        for (String word : words) {
            if (!exclusionList.contains(word)) {
                wordCount.put(word, wordCount.getOrDefault(word, 0) + 1);
            }
        }
        return wordCount;
    }
}
