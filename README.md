# Iterator
```cs
class Iterator {
    private string[] items; private int index=0;
    public Iterator(string[] i){items=i;}
    public string Next()=>index<items.Length?items[index++]:null;
}

class Program {
    static void Main(){
        var it=new Iterator(new[]{"A","B","C"});
        string item; while((item=it.Next())!=null) Console.WriteLine(item);
    }
}
