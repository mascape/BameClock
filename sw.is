const CACHE_NAME = "game-clock-v1";

const urlsToCache = [

  "./",
  "./index.html",

  "./manifest.json",

  "./icon-192.png",
  "./icon-512.png",

  "./warning1.mp3",
  "./warning2.mp3",
  "./finish.mp3"
];

/* =========================
   INSTALL
========================= */

self.addEventListener("install",(event)=>{

  event.waitUntil(

    caches.open(CACHE_NAME)

      .then((cache)=>{

        return cache.addAll(urlsToCache);
      })
  );
});

/* =========================
   FETCH
========================= */

self.addEventListener("fetch",(event)=>{

  event.respondWith(

    caches.match(event.request)

      .then((response)=>{

        return response || fetch(event.request);
      })
  );
});
