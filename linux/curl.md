curl -X GET -i http://url

curl -X POST -i http://url -H "Content-Type: application/json" -d '{"type":"abc","value":123}'

curl -O http://url/file

curl --cookie "CloudFront-Key-Pair-Id=KLF6VW5TBETCE;CloudFront-Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9kdGhsOXF4bWM2YzNyLmNsb3VkZnJvbnQubmV0LyoiLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE2NzEyNjQyMzl9fX1dfQ__;CloudFront-Signature=GfcTLRv~H0JH~-V0PIatS0hIX7YV5fQ8S-CIl5Cbz4cbm30QgbUDBmEu~4H4Hs7ywAR9TDzJfp~uJtbSXGZ0fJGdjfne~ReZ7EOjuZsFVhZcd1Gzt6-r5znEu~S8oKKFo-GI9iAVvwzn~Q2vkr9iNqKyvADFpydhNc06LOYwxL6vEMAfCVXyAhFdd70VKILxWnAP-JVrBZH-iSYfxe3goPFJFqXB1owL1v6mwK1SQhIf64kTBZfeIoBYoY9QBhmzLdPlesCjBuIX11H0XmtPquUJICTZmyUPLkg4sfHaMPw4xaQbmjP2y8mqgkF7xLz2up7HnFaUMKSRen3aluuDPw__" https://cloudfront/playback.m3u8
