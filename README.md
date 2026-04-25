# Damascus-AG-church-app
Church app

Church Member Directory App
===========================

How to Run:
1. Extract the ZIP file.
2. Open index.html in any web browser.

Features:
- Add members
- Delete members
- Search directory
- Saves data locally in browser
- Mobile responsive

No installation required.
Church Member Directory
Name
Phone
Email
Address
Add Member


Damascus Assembly Church Directory Prototype
const CACHE_NAME = 'damascus-app-v1';

const urlsToCache = [
  './',
  './index.html',
  './church_sign.png',
  './icon-192.png',
  './icon-512.png'
];

self.addEventListener('install', event => {
  event.waitUntil(
    caches.open(CACHE_NAME)
      .then(cache => cache.addAll(urlsToCache))
  );
});

self.addEventListener('fetch', event => {
  event.respondWith(
    caches.match(event.request)
      .then(response => response || fetch(event.request))
  );
});
