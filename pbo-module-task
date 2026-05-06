public class Item
{
    public string judul;
    public int tahun;

    public Item(string judul, int tahun)
    {
        this.judul = judul;
        this.tahun = tahun;
    }

    public virtual void Deskripsi()
    {
        Console.WriteLine($"Item berjudul {judul} dipublikasikan pada tahun {tahun}.");
    }

    public void InfoItem()
    {
        Console.WriteLine($"Judul buku {judul} terbit pada tahun {tahun}.");
    }
}
public class Buku : Item
{
    public string penulis;

    public Buku(string judul, int tahun, string penulis) : base(judul, tahun)
    {
        this.penulis = penulis;
    }

    public void CekPenulis()
    {
        Console.WriteLine($"Penulis dari buku {judul} adalah {penulis}.");
    }

    public override void Deskripsi()
    {
        Console.WriteLine($"Buku {judul} ditulis oleh {penulis} dan dipublikasikan pada tahun {tahun}.");
    }
}

public class Majalah : Item
{
    public string edisi;

    public Majalah(string judul, int tahun, string edisi) : base(judul, tahun)
    {
        this.edisi = edisi;
    }

    public void InfoEdisi()
    {
        Console.WriteLine($"Majalah {judul} merupakan edisi {edisi}.");
    }

    public override void Deskripsi()
    {
        Console.WriteLine($"Majalah {judul} pada edisi ke {edisi} dipublikasikan pada tahun {tahun}.");
    }
}
public class Novel : Buku
{
    public Novel(string judul, int tahun, string penulis) : base(judul, tahun, penulis) { }

    public void BacaSinopsis()
    {
        Console.WriteLine($"Sinopsis dari novel {judul} sedang ditampilkan.");
    }

    public override void Deskripsi()
    {
        Console.WriteLine($"Novel {judul} merupakan karya {penulis} yang dipublikasikan pada tahun {tahun}.");
    }
}

public class Komik : Buku
{
    public Komik(string judul, int tahun, string penulis) : base(judul, tahun, penulis) { }

    public void TampilkanIlustrasi()
    {
        Console.WriteLine($"Ilustrasi dari komik {judul} sangat bagus.");
    }

    public override void Deskripsi()
    {
        Console.WriteLine($"Komik {judul} ditulis oleh {penulis} dan dipublikasikan pada tahun {tahun}.");
    }
}

public class MajalahAnak : Majalah
{
    public MajalahAnak(string judul, int tahun, string edisi) : base(judul, tahun, edisi) { }

    public void KategoriAnak()
    {
        Console.WriteLine($"Majalah {judul} termasuk dalam kategori anak-anak.");
    }

    public override void Deskripsi()
    {
        Console.WriteLine($"Majalah anak dengan {judul} edisi {edisi} dipublikasikan pada tahun {tahun}.");
    }
}

public class MajalahTeknologi : Majalah
{
    public MajalahTeknologi(string judul, int tahun, string edisi) : base(judul, tahun, edisi) { }

    public void TopikTeknologi()
    {
        Console.WriteLine($"Majalah {judul} membahas mengenai topik teknologi terbaru.");
    }

    public override void Deskripsi()
    {
        Console.WriteLine($"Majalah teknologi {judul} edisi {edisi} dipublikasikan pada tahun {tahun}.");
    }
}
public class Perpustakaan
{
    private List<Item> koleksi = new List<Item>();

    public void TambahItem(Item item)
    {
        Console.WriteLine($"Item {item.judul} ditambahkan ke perpustakaan.");
        koleksi.Add(item);
    }

    public void DaftarItem()
    {
        Console.WriteLine("\n===Tampilkan Semua Data Buku Perpustakaan===");

        foreach (Item item in koleksi)
        {
            item.Deskripsi(); 
        }
    }
}

class Program
{
    static void Main()
    {
        Perpustakaan perpus = new Perpustakaan();

        Novel novel = new Novel("3726 MDPL", 2024, "Nurwina Sari");
        Komik komik = new Komik("Next G", 2017, "Mizan Publishing");
        MajalahAnak majAnak = new MajalahAnak("Bobo", 2023, "4");
        MajalahTeknologi majtek = new MajalahTeknologi("Inovasi Digital", 2025, "3");

        Console.WriteLine("\n=== Info Item Data Buku Perpustakaan Telah Ditambahkan===");
        perpus.TambahItem(novel);
        perpus.TambahItem(komik);
        perpus.TambahItem(majAnak);
        perpus.TambahItem(majtek);

        perpus.DaftarItem();

        Console.WriteLine("\n=== Demonstrasi Polymorphism ===");

        List<Item> daftarItem = new List<Item>();
        daftarItem.Add(novel);
        daftarItem.Add(komik);
        daftarItem.Add(majAnak);
        daftarItem.Add(majtek);

        foreach (Item itemPoli in daftarItem)
        {
            itemPoli.Deskripsi();
        }

        Item item = new Komik("Next G", 2017, "Mizan Publishing");
        item.Deskripsi();

        Console.WriteLine("\n=== Method Khusus ===");
        novel.BacaSinopsis();
        novel.InfoItem();
        novel.CekPenulis();
        komik.TampilkanIlustrasi();
        komik.InfoItem();
        majAnak.KategoriAnak();
        majAnak.InfoEdisi();
        majtek.TopikTeknologi();
        majtek.InfoEdisi();   
      
    }
}
