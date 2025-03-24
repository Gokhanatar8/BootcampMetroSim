# BootcampMetroSim

Proje, metro istasyonları içerisinden seçilen bir istasyondan hedef istasyona en hızlı veya en az aktarma ile nasıl ulaşılabileceğini hesaplamayı amaçlamaktadır.

Proje Pycharm'da düzenlenmiş, Python sanal ortamı kullanılmıştır.

# Kütüphaneler, teknolojiler: 

Collections içerisindeki defaultdict ve deque -> Collections modülü Python'un temel veri yığınlarından list, tuple vb. için alternatifler oluşturacak özel metodlar barındırır. Defaultdict, varsayılan değer belirler ve KeyError hatasını engeller. Deque ise list yapısının başına ekle-sil işlemleri uygulanmasını sağlar.  

Heapq -> Öncelikli kuyruk oluşturmak için kullanılır. Küçük değer önde döndüğünden en düşük maliyetli düğümü hızlı şekilde bulmak için kullanılabilir.

Typing içerisindeki Dict, List, Set, Tuple, Optional -> Veri tipi için ipucu veren modül. Örneğin list[int], listenin içeriğinde integer değerler olacağını belirtir.

BFS (Breadth-First Search - Genişlik Öncelikli Arama) -> Bir ağaç veya graph üzerinde bir düğüme uğramak için arama yapan algoritma. Düğümleri kuyruk veri yapısını kullanarak katman katman keşfeder.

A* algoritması -> En kısa yolu bulmak için çalışan, her düğüm için maliyet fonksiyonu kullanan bir algoritmadır.

En az aktarma ve en hızlı rotayı bulmak amacımız olduğu için BFS ve A* algoritmaları kullanıma uygun.

# Örnek Uygulama ve sonuç  
    # İstasyonlar ekleme
    # Kırmızı Hat
    metro.istasyon_ekle("K1", "Kızılay", "Kırmızı Hat")
    metro.istasyon_ekle("K2", "Ulus", "Kırmızı Hat")
    metro.istasyon_ekle("K3", "Demetevler", "Kırmızı Hat")
    metro.istasyon_ekle("K4", "OSB", "Kırmızı Hat")
    
    # Mavi Hat
    metro.istasyon_ekle("M1", "AŞTİ", "Mavi Hat")
    metro.istasyon_ekle("M2", "Kızılay", "Mavi Hat")  # Aktarma noktası
    metro.istasyon_ekle("M3", "Sıhhiye", "Mavi Hat")
    metro.istasyon_ekle("M4", "Gar", "Mavi Hat")
    
    # Turuncu Hat
    metro.istasyon_ekle("T1", "Batıkent", "Turuncu Hat")
    metro.istasyon_ekle("T2", "Demetevler", "Turuncu Hat")  # Aktarma noktası
    metro.istasyon_ekle("T3", "Gar", "Turuncu Hat")  # Aktarma noktası
    metro.istasyon_ekle("T4", "Keçiören", "Turuncu Hat")
    
    # Bağlantılar ekleme
    # Kırmızı Hat bağlantıları
    metro.baglanti_ekle("K1", "K2", 4)  # Kızılay -> Ulus
    metro.baglanti_ekle("K2", "K3", 6)  # Ulus -> Demetevler
    metro.baglanti_ekle("K3", "K4", 8)  # Demetevler -> OSB
    
    # Mavi Hat bağlantıları
    metro.baglanti_ekle("M1", "M2", 5)  # AŞTİ -> Kızılay
    metro.baglanti_ekle("M2", "M3", 3)  # Kızılay -> Sıhhiye
    metro.baglanti_ekle("M3", "M4", 4)  # Sıhhiye -> Gar
    
    # Turuncu Hat bağlantıları
    metro.baglanti_ekle("T1", "T2", 7)  # Batıkent -> Demetevler
    metro.baglanti_ekle("T2", "T3", 9)  # Demetevler -> Gar
    metro.baglanti_ekle("T3", "T4", 5)  # Gar -> Keçiören
    
    # Hat aktarma bağlantıları (aynı istasyon farklı hatlar)
    metro.baglanti_ekle("K1", "M2", 2)  # Kızılay aktarma
    metro.baglanti_ekle("K3", "T2", 3)  # Demetevler aktarma
    metro.baglanti_ekle("M4", "T3", 2)  # Gar aktarma
		
	 	# AŞTİ --> OSB rotası
	 	En az aktarmalı rota: AŞTİ -> Kızılay -> Kızılay -> Ulus -> Demetevler -> OSB
		En hızlı rota (25 dakika): AŞTİ -> Kızılay -> Kızılay -> Ulus -> Demetevler -> OSB
		
		# Batıkent --> Sıhhiye rotası
		En az aktarmalı rota: Batıkent -> Demetevler -> Gar -> Gar -> Sıhhiye
		En hızlı rota (22 dakika): Batıkent -> Demetevler -> Gar -> Gar -> Sıhhiye

# Geliştirilebilecek yönler: 

Kodların düzeni ve algoritma hızı üzerinde çalışmalar yapılıp çok daha kapsamlı bir güzergah projesi oluşturulabilir. Bu istasyonlara ek olarak ildeki diğer taşıma araçları, bunların istasyon veya duraklara ne zaman varacağı gibi veriler eklenebilir.
 		
    
