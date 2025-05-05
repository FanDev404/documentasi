[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#table-of-contents)

# FULL DOCUMENTASI WORDING VERSION 3

> Note : jangan salah ya karena ini ada bagian yg di update support semua text dan ada yang ga, dan jika ada keluhan bisa hubungi owner, atau ada request ingin tambahkan sesuatu pada wording



(text, options = {}) => {
    let teks = "";
    let data = {
        "Malam": "Evening", 
        "Pagi": "Morning", 
        "Siang": "Afternoon", 
        "Sore": "Afternoon", 
        "Senin": "Monday", 
        "Selasa": "Tuesday", 
        "Rabu": "Wednesday", 
        "Kamis": "Thursday", 
        "Jumat": "Friday", 
        "Sabtu": "Saturday", 
        "Minggu": "Sunday", 
        "Januari": "January", 
        "Februari": "February", 
        "Maret": "March", 
        "Mei": "May", 
        "Juni": "June", 
        "Juli": "July", 
        "Agustus": "August", 
        "Oktober": "October", 
        "Desember": "December", 
    }
    let kataWaktu = ""
    let timeWib = moment().locale("id").tz("Asia/Jakarta").format("HH:mm:ss")
    let timeWita = moment().locale("id").tz("Asia/Makassar").format("HH:mm:ss")
    let timeWit = moment().locale("id").tz("Asia/Jayapura").format("HH:mm:ss")
    let format_data = text.split("{").map((x) => x.split("}")[0]).filter((x) => x.trim() !== "").map((x) => "{" + x + "}")
    if (format_data.filter((x) => (x.toLowerCase() == "{waktuwita}" || x.toLowerCase() == "{timewita}" || x.toLowerCase() == "{waktu wita}" || x.toLowerCase() == "{time wita}" || x.toLowerCase() == "{waktu_wita}"|| x.toLowerCase() == "{time_wita}" || x.toLowerCase() == "{wita}")).length && format_data.filter((x) => (x.toLowerCase() == "{waktuwit}" || x.toLowerCase() == "{timewit}" || x.toLowerCase() == "{waktu wit}" || x.toLowerCase() == "{time wit}" || x.toLowerCase() == "{waktu_wit}" || x.toLowerCase() == "{time_wit}" || x.toLowerCase() == "{wit}")).length == 0 && format_data.filter((x) => (x.toLowerCase() == "{waktuwib}" || x.toLowerCase() == "{timewib}" || x.toLowerCase() == "{waktu wib}" || x.toLowerCase() == "{time wib}" || x.toLowerCase() == "{waktu_wib}" || x.toLowerCase() == "{time_wib}" || x.toLowerCase() == "{wib}")).length == 0) {
        if (timeWita < "23:59:00") { 
            kataWaktu = "Malam"
        }
        if (timeWita < "19:00:00") { 
            kataWaktu = "Malam"
        }
        if (timeWita < "18:00:00") { 
            kataWaktu = "Sore"
        }
        if (timeWita < "15:00:00") { 
            kataWaktu = "Siang"
        }
        if (timeWita < "11:00:00") { 
            kataWaktu = "Pagi"
        }
        if (timeWita < "06:00:00") { 
            kataWaktu = "Pagi"
        }
    } else if (format_data.filter((x) => (x.toLowerCase() == "{waktuwita}" || x.toLowerCase() == "{timewita}" || x.toLowerCase() == "{waktu wita}" || x.toLowerCase() == "{time wita}" || x.toLowerCase() == "{waktu_wita}"|| x.toLowerCase() == "{time_wita}" || x.toLowerCase() == "{wita}")).length == 0 && format_data.filter((x) => (x.toLowerCase() == "{waktuwit}" || x.toLowerCase() == "{timewit}" || x.toLowerCase() == "{waktu wit}" || x.toLowerCase() == "{time wit}" || x.toLowerCase() == "{waktu_wit}" || x.toLowerCase() == "{time_wit}" || x.toLowerCase() == "{wit}")).length && format_data.filter((x) => (x.toLowerCase() == "{waktuwib}" || x.toLowerCase() == "{timewib}" || x.toLowerCase() == "{waktu wib}" || x.toLowerCase() == "{time wib}" || x.toLowerCase() == "{waktu_wib}" || x.toLowerCase() == "{time_wib}" || x.toLowerCase() == "{wib}")).length == 0) {
        if (timeWit < "23:59:00") { 
            kataWaktu = "Malam"
        }
        if (timeWit < "19:00:00") { 
            kataWaktu = "Malam"
        }
        if (timeWit < "18:00:00") { 
            kataWaktu = "Sore"
        }
        if (timeWit < "15:00:00") { 
            kataWaktu = "Siang"
        }
        if (timeWit < "11:00:00") { 
            kataWaktu = "Pagi"
        }
        if (timeWit < "06:00:00") { 
            kataWaktu = "Pagi"
        }
    } else {
        if (timeWib < "23:59:00") { 
            kataWaktu = "Malam"
        }
        if (timeWib < "19:00:00") { 
            kataWaktu = "Malam"
        }
        if (timeWib < "18:00:00") { 
            kataWaktu = "Sore"
        }
        if (timeWib < "15:00:00") { 
            kataWaktu = "Siang"
        }
        if (timeWib < "11:00:00") { 
            kataWaktu = "Pagi"
        }
        if (timeWib < "06:00:00") { 
            kataWaktu = "Pagi"
        }
    }
    teks = text
    for (const x of format_data) {
        if (x.toLowerCase() == "{waktuwita}" || x.toLowerCase() == "{timewita}" || x.toLowerCase() == "{waktu wita}" || x.toLowerCase() == "{time wita}" || x.toLowerCase() == "{waktu_wita}"|| x.toLowerCase() == "{time_wita}" || x.toLowerCase() == "{wita}") {
            teks = teks.split(x).join(timeWita)
        } else if (x.toLowerCase() == "{waktuwit}" || x.toLowerCase() == "{timewit}" || x.toLowerCase() == "{waktu wit}" || x.toLowerCase() == "{time wit}" || x.toLowerCase() == "{waktu_wit}"|| x.toLowerCase() == "{time_wit}" || x.toLowerCase() == "{wit}") {
            teks = teks.split(x).join(timeWit)
        } else if (x.toLowerCase() == "{waktuwib}" || x.toLowerCase() == "{timewib}" || x.toLowerCase() == "{waktu wib}" || x.toLowerCase() == "{time wib}" || x.toLowerCase() == "{waktu_wib}"|| x.toLowerCase() == "{time_wib}" || x.toLowerCase() == "{wib}") {
            teks = teks.split(x).join(timeWib)
        } else if (x.includes("{kata waktu}") || x.includes("{kata_waktu}") || x.includes("{katawaktu}")) {
            teks = teks.split(x).join(kataWaktu.toLowerCase())
        } else if (x.includes("{Kata waktu}") || x.includes("{Kata_waktu}") || x.includes("{Katawaktu}")) {
            teks = teks.split(x).join(toFirstCase(kataWaktu))
        } else if (x.includes("{KATA WAKTU}") || x.includes("{KATA_WAKTU}") || x.includes("{KATAWAKTU}")) {
            teks = teks.split(x).join(kataWaktu.toUpperCase())
        } else if (x.includes("{said time}") || x.includes("{said times}") || x.includes("{said_time}") || x.includes("{said_times}") || x.includes("{saidtime}") || x.includes("{saidtimes}")) {
            teks = teks.split(x).join(Object.keys(data).includes(kataWaktu)? data[kataWaktu].toLowerCase() : kataWaktu.toLowerCase())
        } else if (x.includes("{Said time}") || x.includes("{Said times}") || x.includes("{Said_time}") || x.includes("{Said_times}") || x.includes("{Saidtime}") || x.includes("{Saidtimes}")) {
            teks = teks.split(x).join(Object.keys(data).includes(kataWaktu)? toFirstCase(data[kataWaktu]) : toFirstCase(kataWaktu))
        } else if (x.includes("{SAID TIME}") || x.includes("{SAID TIMES}") || x.includes("{SAID_TIME}") || x.includes("{SAID_TIMES}") || x.includes("{SAIDTIME}") || x.includes("{SAIDTIMES}")) {
            teks = teks.split(x).join(Object.keys(data).includes(kataWaktu)? data[kataWaktu].toUpperCase() : kataWaktu.toUpperCase())
        } else if (x.includes("{hari}")) {
            teks = teks.split(x).join(moment().locale("id").tz("Asia/Jakarta").format("dddd").toLowerCase())
        } else if (x.includes("{Hari}")) {
            teks = teks.split(x).join(toFirstCase(moment().locale("id").tz("Asia/Jakarta").format("dddd")))
        } else if (x.includes("{HARI}")) {
            teks = teks.split(x).join(moment().locale("id").tz("Asia/Jakarta").format("dddd").toUpperCase())
        } else if (x.includes("{day}") || x.includes("{days}")) {
            teks = teks.split(x).join(Object.keys(data).includes(moment().locale("id").tz("Asia/Jakarta").format("dddd"))? data[moment().locale("id").tz("Asia/Jakarta").format("dddd")].toLowerCase() : moment().locale("id").tz("Asia/Jakarta").format("dddd").toLowerCase())
        } else if (x.includes("{Day}") || x.includes("{Days}")) {
            teks = teks.split(x).join(Object.keys(data).includes(moment().locale("id").tz("Asia/Jakarta").format("dddd"))? toFirstCase(data[moment().locale("id").tz("Asia/Jakarta").format("dddd")]) : toFirstCase(moment().locale("id").tz("Asia/Jakarta").format("dddd")))
        } else if (x.includes("{DAY}") || x.includes("{DAYS}")) {
            teks = teks.split(x).join(Object.keys(data).includes(moment().locale("id").tz("Asia/Jakarta").format("dddd"))? data[moment().locale("id").tz("Asia/Jakarta").format("dddd")].toUpperCase() : moment().locale("id").tz("Asia/Jakarta").format("dddd").toUpperCase())
        } else if (x.includes("{bulan}")) {
            teks = teks.split(x).join(moment().locale("id").tz("Asia/Jakarta").format("MMMM").toLowerCase())
        } else if (x.includes("{Bulan}")) {
            teks = teks.split(x).join(toFirstCase(moment().locale("id").tz("Asia/Jakarta").format("MMMM").toLowerCase()))
        } else if (x.includes("{BULAN}")) {
            teks = teks.split(x).join(moment().locale("id").tz("Asia/Jakarta").format("MMMM").toUpperCase())
        } else if (x.includes("{month}") || x.includes("{months}")) {
            teks = teks.split(x).join(Object.keys(data).includes(moment().locale("id").tz("Asia/Jakarta").format("MMMM"))? data[moment().locale("id").tz("Asia/Jakarta").format("MMMM")].toLowerCase() : moment().locale("id").tz("Asia/Jakarta").format("MMMM").toLowerCase())
        } else if (x.includes("{Month}") || x.includes("{Months}")) {
            teks = teks.split(x).join(Object.keys(data).includes(moment().locale("id").tz("Asia/Jakarta").format("MMMM"))? toFirstCase(data[moment().locale("id").tz("Asia/Jakarta").format("MMMM")]) : toFirstCase(moment().locale("id").tz("Asia/Jakarta").format("MMMM")))
        } else if (x.includes("{MONTHS}") || x.includes("{MONTHS}")) {
            teks = teks.split(x).join(Object.keys(data).includes(moment().locale("id").tz("Asia/Jakarta").format("MMMM"))? data[moment().locale("id").tz("Asia/Jakarta").format("MMMM")].toUpperCase() : moment().locale("id").tz("Asia/Jakarta").format("MMMM").toUpperCase())
        } else if (x.toLowerCase().includes("{date}") || x.toLowerCase().includes("{dates}")|| x.toLowerCase().includes("{tanggal}")) {
            teks = teks.split(x).join(moment().locale("id").tz("Asia/Jakarta").format("DD"))
        } else if (x.toLowerCase().includes("{year}") || x.toLowerCase().includes("{years}") || x.toLowerCase().includes("{tahun}")) {
            teks = teks.split(x).join(moment().locale("id").tz("Asia/Jakarta").format("YYYY"))
        } else if (x.toLowerCase().includes("{calender2}") || x.toLowerCase().includes("{calendar2}") || x.toLowerCase().includes("{kalender2}")) {
            teks = teks.split(x).join(moment().locale("id").tz("Asia/Jakarta").format("DD/MM/YYYY"))
        } else if (x.toLowerCase().includes("{calender}") || x.toLowerCase().includes("{calendar}") || x.toLowerCase().includes("{kalender}")) {
            teks = teks.split(x).join(moment().locale("id").tz("Asia/Jakarta").format("DD-MM-YYYY"))
        } else if (options[x.toLowerCase().replace("{", "").replace("}", "")]) {
            teks = teks.split(x).join(options[x.toLowerCase().replace("{", "").replace("}", "")])
        }
    }
    return teks
}

# waktu bagian wita
> Results : 00:00:00
> Note : Format support all (auto dalam artian huruf mau besar kecil bisa semuanya) 
```
{waktuwita}
```
```
{waktu wita}
```
```
{waktu_wita}
```
```
{timewita}
```
```
{time wita}
```
```
{time_wita}
```
```
{wita}
```

