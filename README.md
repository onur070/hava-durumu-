# hava-durumu-
const apiKey = "87476094af2064261994f1e923d2bf2d";
const buton = document.getElementById("araButon");

buton.addEventListener("click", () => {
    const sehir = document.getElementById("sehirInput").value;
    const url = `https://api.openweathermap.org/data/2.5/weather?q=${sehir}&appid=${apiKey}&units=metric&lang=tr`;

    fetch(url)
        .then(res => res.json())
        .then(data => {
            document.getElementById("sonuc").innerHTML = `
                <h3>${data.name}</h3>
                <p>Sıcaklık: ${data.main.temp}°C</p>
                <p>Durum: ${data.weather[0].description}</p>
            `;
        })
        .catch(() => alert("Şehir bulunamadı!"));
});
