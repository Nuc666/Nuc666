public class testclass {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        TreeMap <String, TreeSet<String>> frends = new TreeMap<>();
        while (in.hasNextLine()){
            String s = in.nextLine();
            if (s.isEmpty()) break;
            else {
                String [] ss = s.split(" ");
                String str1 = ss[0];
                String str2 = ss[1];
                String str3 = ss[2];
                String str4 = ss[3];
                String name = new StringBuilder().append(ss[0]).append(" ").append(ss[1]).toString();
                String name2 = new StringBuilder().append(ss[2]).append(" ").append(ss[3]).toString();

                if (frends.containsKey(name)) frends.get(name).add(name2);
                else {
                    TreeSet<String> set = new TreeSet<String>();
                    set.add(name2);
                    frends.put(name, set);
                }
            }
        }
        for (String name3 : frends.keySet()){
            System.out.println(name3+":");
            for (String name4 : frends.get(name3)){
                System.out.println("    "+name4);
            }
        }

    }
}
