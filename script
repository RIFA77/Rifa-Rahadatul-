
        //  Jelaskan Kodingan ini apa 
        document.addEventListener('DOMContentLoaded', function() {
        // itu fungsinya buat jalanin JavaScript setelah semua elemen HTML-nya selesai dimuat. Jadi script-nya nggak nyalain apa-apa sebelum halaman siap, biar nggak error karena elemennya belum kebaca.

            //  Jelaskan Kodingan ini apa 
             // Kode ini digunakan untuk mengakses elemen-elemen yang diperlukan dalam kalkulator.
            const display = document.getElementById('display'); //display digunakan untuk mengakses layar tempat angka ditampilkan.
            const statusImage = document.getElementById('statusImage'); //statusImage digunakan untuk menghubungkan script dengan gambar status kalkulator.
            const buttons = document.querySelectorAll('.btn-calc'); //buttons digunakan untuk mengumpulkan semua tombol yang punya class .btn-calc, supaya nanti bisa diproses satu per satu.


            //  Jelaskan Kodingan ini apa 
            // Kode ini berisi tiga variabel yang masing-masing menyimpan link gambar. Fungsinya buat mengubah tampilan gambar kalkulator sesuai kondisi:
            const imgNormal = 'https://placehold.co/400x100/374151/E5E7EB?text=Kalkulator'; //gambar default kalkulator.
            const imgSuccess = 'https://placehold.co/400x100/16A34A/FFFFFF?text=Sukses!'; //gambar yang muncul kalau perhitungannya berhasil.
            const imgError = 'https://placehold.co/400x100/DC2626/FFFFFF?text=Error!'; //imgError → gambar yang muncul kalau ada kesalahan.

            /**
              Jelaskan Kodingan ini apa 
             */
            // Fungsi changeImage() ini dipakai untuk mengganti gambar status kalkulator berdasarkan keadaan. Kalau state-nya success, gambarnya diganti ke gambar sukses. Kalau state-nya ‘error’, gambarnya diganti ke gambar error. Kalau bukan dua-duanya, dia balikin lagi ke gambar normal. Intinya, fungsi ini ngatur supaya tampilan gambar bisa menyesuaikan kondisi kalkulator.
            function changeImage(state) {
                if (state === 'success') {
                    statusImage.src = imgSuccess;
                    statusImage.alt = "Perhitungan Sukses";
                } else if (state === 'error') {
                    statusImage.src = imgError;
                    statusImage.alt = "Error Perhitungan";
                } else {
                    //  Jelaskan Kodingan ini apa 
                    statusImage.src = imgNormal;
                    statusImage.alt = "Status Kalkulator";
                }
            }
            //Bagian kode ini dipakai ketika kondisinya kembali ke default. Jadi gambarnya diset ulang ke gambar normal (imgNormal), dan teks alternatifnya juga diset jadi "Status Kalkulator". Intinya: ini buat nge-reset tampilan gambar ke keadaan awal.

            /**
              Jelaskan Kodingan ini apa 
             */
            function clearDisplay() { //ini dipakai untuk menghapus isi layar kalkulator.
                display.value = ''; //ini dipakai untuk menghapus isi layar kalkulator.
                changeImage('normal'); // Memanggil function untuk merubah gambar //dipanggil untuk balikin gambar ke kondisi normal setelah layarnya dibersihkan.
            }

            /**
              Jelaskan Kodingan ini apa 
             */
            function deleteLastChar() { //ini dipakai untuk menghapus satu karakter terakhir di layar kalkulator.
                display.value = display.value.slice(0, -1); //artinya dia cuma ngambil tulisan dari awal sampai sebelum karakter terakhir, jadi angka atau simbol paling belakang bakal hilang. Intinya: fitur DEL → hapus satu per satu dari belakang.
            }

            /**
              Jelaskan Kodingan ini apa 
             */
            function appendToDisplay(value) {
                display.value += value;
            } //ini fungsinya buat nambahin angka atau simbol ke layar kalkulator. Jadi setiap kali tombol ditekan, nilai tombol itu bakal langsung ditempel ke belakang isi display.

            /**
              Jelaskan Kodingan ini apa 
             */
            function calculateResult() { //ini adalah fungsi utama yang nantinya dipakai untuk menghitung hasil dari operasi yang ada di layar kalkulator. Jadi kalau user menekan tombol "=", fungsi inilah yang bakal dijalankan untuk memproses perhitungan dan menampilkan hasilnya ke display.
                //  Jelaskan Kodingan ini apa 
                if (display.value === '') {
                    changeImage('error');
                    display.value = 'Kosong!'; //Bagian kode ini dipakai untuk ngecek apakah layar kalkulator masih kosong waktu tombol = ditekan. Kalau isinya kosong, maka: Gambarnya diganti jadi error lewat changeImage('error'). Layar kalkulator ditampilkan tulisan "Kosong!" biar pengguna tahu kalau nggak ada angka yang bisa dihitung.
                    //  Jelaskan Kodingan ini apa 
                    setTimeout(clearDisplay, 1500); // Baris ini buat menunggu 1,5 detik sebelum fungsi clearDisplay() dijalankan. Jadi setelah layar muncul tulisan "Kosong!", kalkulator bakal otomatis nge-reset setelah 1,5 detik.
                    return; // Ini dipakai untuk menghentikan fungsi di sini, supaya kode setelahnya nggak dijalankan.
                }

                try { //ini dipakai untuk menjalankan kode yang berpotensi error dengan cara yang aman.
                    //  Jelaskan Kodingan ini apa 
                    let result = eval(display.value //Bagian ini dipakai untuk mengubah tanda persen (%) menjadi /100. Jadi kalau user ngetik 50%, itu otomatis diubah jadi 50/100 supaya bisa dihitung oleh JavaScript.
                        //Setelah itu, seluruh isi display yang sudah diolah tadi dihitung oleh fungsi eval(). eval akan membaca teks perhitungan (misalnya "5+5*2") lalu mengubahnya jadi hasil angka.
                        //let result = ... Hasil perhitungan disimpan ke dalam variabel result.
                        .replace(/%/g, '/100') //  Jelaskan Kodingan ini apa 
                    );  //fungsinya buat mengganti semua tanda persen (%) menjadi /100. Tujuannya supaya angka persen bisa dihitung sebagai operasi matematika.
                    
                    //  Jelaskan Kodingan ini apa 
                    if (isFinite(result)) {
                        display.value = result; //Bagian ini dipakai untuk ngecek apakah hasil perhitungan itu angka yang valid. isFinite(result) akan mengembalikan true kalau hasilnya bukan NaN atau Infinity. Kalau valid, hasilnya langsung ditampilkan ke layar kalkulator.
                        changeImage('success'); //  Jelaskan Kodingan ini apa  //Bagian ini buat mengganti gambar status jadi sukses kalau hasil perhitungan valid.
                    } else {
                        throw new Error("Hasil tidak valid"); //Kalau hasilnya nggak valid, kode melempar error supaya langsung masuk ke bagian catch.
                    }

                } catch (error) {
                    console.error("Error kalkulasi:", error);
                    display.value = 'Error'; //Bagian catch ini akan jalan kalau terjadi kesalahan. Error dicatat di console (buat debugging). Layar kalkulator ditampilkan tulisan "Error" biar pengguna tahu ada masalah.
                    changeImage('error'); //  Jelaskan Kodingan ini apa  //Bagian ini buat mengganti gambar status jadi error waktu perhitungannya gagal.
                    setTimeout(clearDisplay, 1500); //Ini untuk membersihkan layar kalkulator otomatis setelah 1,5 detik, supaya tampilannya balik normal lagi.
                }
            }


            //  Jelaskan Kodingan ini apa 
            buttons.forEach(button => { //Ini buat ngelakuin aksi ke setiap tombol kalkulator yang punya class .btn-calc.
                button.addEventListener('click', () => { //Di sini setiap tombol dikasih event click, jadi kalau tombol ditekan, fungsi di dalamnya akan jalan.
                    const value = button.getAttribute('data-value'); //Bagian ini buat ngambil nilai dari tombol (misalnya 1, +, DEL), sesuai atribut data-value.

                    //  Jelaskan Kodingan ini apa 
                    switch(value) { //ini dipakai untuk mengecek nilai tombol yang ditekan. Jadi nanti setiap tombol punya aksi berbeda sesuai nilainya.
                        case 'C': // Kalau tombol yang ditekan adalah C, maka kalkulator akan menjalankan perintah khusus untuk tombol Clear.
                            deleteLastChar(); //Ini dijalankan kalau tombol DEL ditekan. Fungsinya buat menghapus satu karakter terakhir di layar kalkulator.
                            break; //Dipakai untuk menghentikan case ini supaya tidak lanjut ke case lain.
                            case 'DEL':
                           
                            // Memanggil function untuk menghapus karakter terakhir
                            deleteLastChar();
                            break;
                            case '=': //Baris ini berarti: kalau tombol yang ditekan adalah tombol "=", maka kalkulator akan masuk ke bagian khusus untuk menghitung hasilnya.
                            //  Jelaskan Kodingan ini apa 
                            calculateResult(); //Ini dipanggil kalau tombol yang ditekan adalah "=". Fungsinya untuk menghitung hasil dari operasi yang ada di layar.
                            break; // Supaya setelah selesai menghitung, kode nggak lanjut ke case lain.
                        default: //Bagian default ini akan dijalankan kalau tombol yang ditekan bukan C, DEL, atau "=". Biasanya untuk tombol angka dan operator biasa.
                            //  Jelaskan Kodingan ini apa 
                            if (statusImage.src === imgSuccess || statusImage.src === imgError) { //Ini ngecek apakah gambar kalkulator lagi dalam kondisi sukses atau error. Kalau iya → artinya perhitungan sebelumnya sudah selesai atau ada kesalahan.
                                clearDisplay(); //Karena statusnya bukan normal lagi, layar kalkulator dibersihin dulu sebelum nerima input baru.
                            }
                            appendToDisplay(value); //Setelah layar kembali normal, nilai tombol yang ditekan ditampilkan ke display.
                            break; //Menghentikan case supaya tidak lanjut ke bagian lain.
                    }
                });
            });

            //  Jelaskan Kodingan ini apa 
            document.addEventListener('keydown', (e) => { //Bagian ini dipakai untuk membaca keyboard. Jadi kalkulator bisa dipakai bukan cuma klik tombol, tapi juga ketik langsung di keyboard.
                const key = e.key;
                if (key >= '0' && key <= '9' || key === '.' || key === '+' || key === '-' || key === '*' || key === '/' || key === '%') {
                    if (statusImage.src === imgSuccess || statusImage.src === imgError) {
                        clearDisplay();
                    }
                    appendToDisplay(key);
                    e.preventDefault(); //Kalau yang ditekan itu angka atau simbol (+ - * / . %), maka: Kalau status gambar lagi sukses/error → layar dibersihkan dulu. Setelah itu karakter yang ditekan ditambah ke display. preventDefault() biar browser nggak ngasih aksi bawaan.
                } else if (key === 'Enter' || key === '=') { //Ini buat menghitung hasil lewat keyboard.
                    calculateResult();
                    e.preventDefault();
                } else if (key === 'Backspace') { //Fungsinya sama kaya tombol DEL → hapus satu karakter terakhir.
                    deleteLastChar();
                    e.preventDefault();
                } else if (key === 'Escape' || key.toLowerCase() === 'c') { //Ini buat Clear, sama kaya tombol C di kalkulator.
                    clearDisplay();
                    e.preventDefault();
                }
            });

        });
