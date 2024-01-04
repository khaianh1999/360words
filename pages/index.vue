<script setup>
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'
const arrWords = [
  {
    "stt": 1,
    "base_form": "abide",
    "past_simple": "abode/abided",
    "past_participle": "abode/abided",
    "define": "lưu trú, lưu lại"
  },
  {
    "stt": 2,
    "base_form": "arise",
    "past_simple": "arose",
    "past_participle": "arisen",
    "define": "phát sinh"
  },
  {
    "stt": 3,
    "base_form": "awake",
    "past_simple": "awoke",
    "past_participle": "awoken",
    "define": "đánh thức, thức"
  },
  {
    "stt": 4,
    "base_form": "backslide",
    "past_simple": "backslid",
    "past_participle": "backslidden/backslid",
    "define": "tái phạm"
  },
  {
    "stt": 5,
    "base_form": "be",
    "past_simple": "was/were",
    "past_participle": "been",
    "define": "thì, là, bị, ở"
  },
  {
    "stt": 6,
    "base_form": "bear",
    "past_simple": "bore",
    "past_participle": "borne",
    "define": "mang, chịu đựng"
  },
  {
    "stt": 7,
    "base_form": "beat",
    "past_simple": "beat",
    "past_participle": "beaten/beat",
    "define": "đánh, đập"
  },
  {
    "stt": 8,
    "base_form": "become",
    "past_simple": "became",
    "past_participle": "become",
    "define": "trở nên"
  },
  {
    "stt": 9,
    "base_form": "befall",
    "past_simple": "befell",
    "past_participle": "befallen",
    "define": "xảy đến"
  },
  {
    "stt": 10,
    "base_form": "begin",
    "past_simple": "began",
    "past_participle": "begun",
    "define": "bắt đầu"
  },
  {
    "stt": 11,
    "base_form": "behold",
    "past_simple": "beheld",
    "past_participle": "beheld",
    "define": "ngắm nhìn"
  },
  {
    "stt": 12,
    "base_form": "bend",
    "past_simple": "bent",
    "past_participle": "bent",
    "define": "bẻ cong"
  },
  {
    "stt": 13,
    "base_form": "beset",
    "past_simple": "beset",
    "past_participle": "beset",
    "define": "bao quanh"
  },
  {
    "stt": 14,
    "base_form": "bespeak",
    "past_simple": "bespoke",
    "past_participle": "bespoken",
    "define": "chứng tỏ"
  },
  {
    "stt": 15,
    "base_form": "bet",
    "past_simple": "bet/betted",
    "past_participle": "bet/betted",
    "define": "đánh cược, cá cược"
  },
  {
    "stt": 16,
    "base_form": "bid",
    "past_simple": "bid",
    "past_participle": "bid",
    "define": "trả giá"
  },
  {
    "stt": 17,
    "base_form": "bind",
    "past_simple": "bound",
    "past_participle": "bound",
    "define": "buộc, trói"
  },
  {
    "stt": 18,
    "base_form": "bite",
    "past_simple": "bit",
    "past_participle": "bitten",
    "define": "cắn"
  },
  {
    "stt": 19,
    "base_form": "bleed",
    "past_simple": "bled",
    "past_participle": "bled",
    "define": "chảy máu"
  },
  {
    "stt": 20,
    "base_form": "blow",
    "past_simple": "blew",
    "past_participle": "blown",
    "define": "thổi"
  },
  {
    "stt": 21,
    "base_form": "break",
    "past_simple": "broke",
    "past_participle": "broken",
    "define": "đập vỡ"
  },
  {
    "stt": 22,
    "base_form": "breed",
    "past_simple": "bred",
    "past_participle": "bred",
    "define": "nuôi, dạy dỗ"
  },
  {
    "stt": 23,
    "base_form": "bring",
    "past_simple": "brought",
    "past_participle": "brought",
    "define": "mang"
  },
  {
    "stt": 24,
    "base_form": "broadcast",
    "past_simple": "broadcast",
    "past_participle": "broadcast",
    "define": "phát thanh"
  },
  {
    "stt": 25,
    "base_form": "browbeat",
    "past_simple": "browbeat",
    "past_participle": "browbeaten/browbeat",
    "define": "dọa nạt"
  },
  {
    "stt": 26,
    "base_form": "build",
    "past_simple": "built",
    "past_participle": "built",
    "define": "xây dựng"
  },
  {
    "stt": 27,
    "base_form": "burn",
    "past_simple": "burnt/burned",
    "past_participle": "burnt/burned",
    "define": "đốt, cháy"
  },
  {
    "stt": 28,
    "base_form": "burst",
    "past_simple": "burst",
    "past_participle": "burst",
    "define": "nổ tung, vỡ òa"
  },
  {
    "stt": 29,
    "base_form": "bust",
    "past_simple": "busted/bust",
    "past_participle": "busted/bust",
    "define": "làm vỡ"
  },
  {
    "stt": 30,
    "base_form": "buy",
    "past_simple": "bought",
    "past_participle": "bought",
    "define": "mua"
  },
  {
    "stt": 31,
    "base_form": "cast",
    "past_simple": "cast",
    "past_participle": "cast",
    "define": "ném, tung"
  },
  {
    "stt": 32,
    "base_form": "catch",
    "past_simple": "caught",
    "past_participle": "caught",
    "define": "bắt, chụp"
  },
  {
    "stt": 33,
    "base_form": "chide",
    "past_simple": "chid/chided",
    "past_participle": "chid/chidden/chided",
    "define": "mắng, chửi"
  },
  {
    "stt": 34,
    "base_form": "choose",
    "past_simple": "chose",
    "past_participle": "chosen",
    "define": "chọn"
  },
  {
    "stt": 35,
    "base_form": "cleave",
    "past_simple": "clove/cleft/cleaved",
    "past_participle": "cloven/cleft/cleaved",
    "define": "chẻ, tách làm đôi"
  },
  {
    "stt": 36,
    "base_form": "cleave",
    "past_simple": "clave",
    "past_participle": "cleaved",
    "define": "dính chặt"
  },
  {
    "stt": 37,
    "base_form": "cling",
    "past_simple": "clung",
    "past_participle": "clung",
    "define": "bám vào, dính vào"
  },
  {
    "stt": 38,
    "base_form": "clothe",
    "past_simple": "clothed/clad",
    "past_participle": "clothed/clad",
    "define": "mặc quần áo, che phủ"
  },
  {
    "stt": 39,
    "base_form": "come",
    "past_simple": "came",
    "past_participle": "come",
    "define": "đến, đi đến"
  },
  {
    "stt": 40,
    "base_form": "cost",
    "past_simple": "cost",
    "past_participle": "cost",
    "define": "có giá là"
  },
  {
    "stt": 41,
    "base_form": "creep",
    "past_simple": "crept",
    "past_participle": "crept",
    "define": "bò, trườn, lẻn"
  },
  {
    "stt": 42,
    "base_form": "crossbreed",
    "past_simple": "crossbred",
    "past_participle": "crossbred",
    "define": "cho lai giống"
  },
  {
    "stt": 43,
    "base_form": "crow",
    "past_simple": "crew/crewed",
    "past_participle": "crowed",
    "define": "gáy (gà)"
  },
  {
    "stt": 44,
    "base_form": "cut",
    "past_simple": "cut",
    "past_participle": "cut",
    "define": "cắt, chặt"
  },
  {
    "stt": 45,
    "base_form": "daydream",
    "past_simple": "daydreamed",
    "past_participle": "daydreamed",
    "define": "mơ mộng"
  },
  {
    "stt": "",
    "base_form": "",
    "past_simple": "daydreamt",
    "past_participle": "daydreamt",
    "define": ""
  },
  {
    "stt": 46,
    "base_form": "deal",
    "past_simple": "dealt",
    "past_participle": "dealt",
    "define": "giao thiệp, xử lý"
  },
  {
    "stt": 47,
    "base_form": "dig",
    "past_simple": "dug",
    "past_participle": "dug",
    "define": "đào"
  },
  {
    "stt": 48,
    "base_form": "disprove",
    "past_simple": "disproved",
    "past_participle": "disproved/disproven",
    "define": "bác bỏ"
  },
  {
    "stt": 49,
    "base_form": "dive",
    "past_simple": "dove/dived",
    "past_participle": "dived",
    "define": "lặn, lao xuống"
  },
  {
    "stt": 50,
    "base_form": "do",
    "past_simple": "did",
    "past_participle": "done",
    "define": "làm"
  },
  {
    "stt": 51,
    "base_form": "draw",
    "past_simple": "drew",
    "past_participle": "drawn",
    "define": "vẽ, kéo"
  },
  {
    "stt": 52,
    "base_form": "dream",
    "past_simple": "dreamt/dreamed",
    "past_participle": "dreamt/dreamed",
    "define": "mơ thấy"
  },
  {
    "stt": 53,
    "base_form": "drink",
    "past_simple": "drank",
    "past_participle": "drunk",
    "define": "uống"
  },
  {
    "stt": 54,
    "base_form": "drive",
    "past_simple": "drove",
    "past_participle": "driven",
    "define": "lái xe"
  },
  {
    "stt": 55,
    "base_form": "dwell",
    "past_simple": "dwelt",
    "past_participle": "dwelt",
    "define": "trú ngụ, ở"
  },
  {
    "stt": 56,
    "base_form": "eat",
    "past_simple": "ate",
    "past_participle": "eaten",
    "define": "ăn"
  },
  {
    "stt": 57,
    "base_form": "fall",
    "past_simple": "fell",
    "past_participle": "fallen",
    "define": "ngã, rơi"
  },
  {
    "stt": 58,
    "base_form": "feed",
    "past_simple": "fed",
    "past_participle": "fed",
    "define": "cho ăn, ăn, nuôi"
  },
  {
    "stt": 59,
    "base_form": "feel",
    "past_simple": "felt",
    "past_participle": "felt",
    "define": "cảm thấy"
  },
  {
    "stt": 60,
    "base_form": "fight",
    "past_simple": "fought",
    "past_participle": "fought",
    "define": "chiến đấu"
  },
  {
    "stt": 61,
    "base_form": "find",
    "past_simple": "found",
    "past_participle": "found",
    "define": "tìm thấy, thấy"
  },
  {
    "stt": 62,
    "base_form": "fit",
    "past_simple": "fitted/fit",
    "past_participle": "fitted/fit",
    "define": "làm cho vừa, làm cho hợp"
  },
  {
    "stt": 63,
    "base_form": "flee",
    "past_simple": "fled",
    "past_participle": "fled",
    "define": "chạy trốn"
  },
  {
    "stt": 64,
    "base_form": "fling",
    "past_simple": "flung",
    "past_participle": "flung",
    "define": "tung, quăng"
  },
  {
    "stt": 65,
    "base_form": "fly",
    "past_simple": "flew",
    "past_participle": "flown",
    "define": "bay"
  },
  {
    "stt": 66,
    "base_form": "forbear",
    "past_simple": "forbore",
    "past_participle": "forborne",
    "define": "nhịn"
  },
  {
    "stt": 67,
    "base_form": "forbid",
    "past_simple": "forbade/forbad",
    "past_participle": "forbidden",
    "define": "cấm, cấm đoán"
  },
  {
    "stt": 68,
    "base_form": "forecast",
    "past_simple": "forecast/forecasted",
    "past_participle": "forecast/forecasted",
    "define": "tiên đoán"
  },
  {
    "stt": 69,
    "base_form": "forego (also forgo)",
    "past_simple": "forewent",
    "past_participle": "foregone",
    "define": "bỏ, kiêng"
  },
  {
    "stt": 70,
    "base_form": "foresee",
    "past_simple": "foresaw",
    "past_participle": "forseen",
    "define": "thấy trước"
  },
  {
    "stt": 71,
    "base_form": "foretell",
    "past_simple": "foretold",
    "past_participle": "foretold",
    "define": "đoán trước"
  },
  {
    "stt": 72,
    "base_form": "forget",
    "past_simple": "forgot",
    "past_participle": "forgotten",
    "define": "quên"
  },
  {
    "stt": 73,
    "base_form": "forgive",
    "past_simple": "forgave",
    "past_participle": "forgiven",
    "define": "tha thứ"
  },
  {
    "stt": 74,
    "base_form": "forsake",
    "past_simple": "forsook",
    "past_participle": "forsaken",
    "define": "ruồng bỏ"
  },
  {
    "stt": 75,
    "base_form": "freeze",
    "past_simple": "froze",
    "past_participle": "frozen",
    "define": "làm đông lại"
  },
  {
    "stt": 76,
    "base_form": "frostbite",
    "past_simple": "frostbit",
    "past_participle": "frostbitten",
    "define": "bỏng lạnh"
  },
  {
    "stt": 77,
    "base_form": "get",
    "past_simple": "got",
    "past_participle": "got/gotten",
    "define": "có được"
  },
  {
    "stt": 78,
    "base_form": "gild",
    "past_simple": "gilt/gilded",
    "past_participle": "gilt/gilded",
    "define": "mạ vàng"
  },
  {
    "stt": 79,
    "base_form": "gird",
    "past_simple": "girt/girded",
    "past_participle": "girt/girded",
    "define": "đeo vào"
  },
  {
    "stt": 80,
    "base_form": "give",
    "past_simple": "gave",
    "past_participle": "given",
    "define": "cho"
  },
  {
    "stt": 81,
    "base_form": "go",
    "past_simple": "went",
    "past_participle": "gone",
    "define": "đi"
  },
  {
    "stt": 82,
    "base_form": "grind",
    "past_simple": "ground",
    "past_participle": "ground",
    "define": "nghiền, xay"
  },
  {
    "stt": 83,
    "base_form": "grow",
    "past_simple": "grew",
    "past_participle": "grown",
    "define": "mọc, trồng"
  },
  {
    "stt": 84,
    "base_form": "hand-feed",
    "past_simple": "hand-fed",
    "past_participle": "hand-fed",
    "define": "cho ăn bằng tay"
  },
  {
    "stt": 85,
    "base_form": "handwrite",
    "past_simple": "handwrote",
    "past_participle": "handwritten",
    "define": "viết tay"
  },
  {
    "stt": 86,
    "base_form": "hang",
    "past_simple": "hung",
    "past_participle": "hung",
    "define": "móc lên, treo lên"
  },
  {
    "stt": 87,
    "base_form": "have",
    "past_simple": "had",
    "past_participle": "had",
    "define": "có"
  },
  {
    "stt": 88,
    "base_form": "hear",
    "past_simple": "heard",
    "past_participle": "heard",
    "define": "nghe"
  },
  {
    "stt": 89,
    "base_form": "heave",
    "past_simple": "hove/heaved",
    "past_participle": "hove/heaved",
    "define": "trục lên"
  },
  {
    "stt": 90,
    "base_form": "hew",
    "past_simple": "hewed",
    "past_participle": "hewn/hewed",
    "define": "chặt, đốn"
  },
  {
    "stt": 91,
    "base_form": "hide",
    "past_simple": "hid",
    "past_participle": "hidden",
    "define": "giấu, trốn, nấp"
  },
  {
    "stt": 92,
    "base_form": "hit",
    "past_simple": "hit",
    "past_participle": "hit",
    "define": "đụng"
  },
  {
    "stt": 93,
    "base_form": "hurt",
    "past_simple": "hurt",
    "past_participle": "hurt",
    "define": "làm đau"
  },
  {
    "stt": 94,
    "base_form": "inbreed",
    "past_simple": "inbred",
    "past_participle": "inbred",
    "define": "lai giống cận huyết"
  },
  {
    "stt": 95,
    "base_form": "inlay",
    "past_simple": "inlaid",
    "past_participle": "inlaid",
    "define": "cẩn, khảm"
  },
  {
    "stt": 96,
    "base_form": "input",
    "past_simple": "input",
    "past_participle": "input",
    "define": "đưa vào"
  },
  {
    "stt": 97,
    "base_form": "inset",
    "past_simple": "inset",
    "past_participle": "inset",
    "define": "dát, ghép"
  },
  {
    "stt": 98,
    "base_form": "interbreed",
    "past_simple": "interbred",
    "past_participle": "interbred",
    "define": "giao phối, lai giống"
  },
  {
    "stt": 99,
    "base_form": "interweave",
    "past_simple": "interwove",
    "past_participle": "interwoven",
    "define": "trộn lẫn, xen lẫn"
  },
  {
    "stt": "",
    "base_form": "",
    "past_simple": "interweaved",
    "past_participle": "interweaved",
    "define": ""
  },
  {
    "stt": 100,
    "base_form": "interwind",
    "past_simple": "interwound",
    "past_participle": "interwound",
    "define": "cuộn vào, quấn vào"
  },
  {
    "stt": 101,
    "base_form": "jerry-build",
    "past_simple": "jerry-built",
    "past_participle": "jerry-built",
    "define": "xây dựng cẩu thả"
  },
  {
    "stt": 102,
    "base_form": "keep",
    "past_simple": "kept",
    "past_participle": "kept",
    "define": "giữ"
  },
  {
    "stt": 103,
    "base_form": "kneel",
    "past_simple": "knelt/kneeled",
    "past_participle": "knelt/kneeled",
    "define": "quỳ"
  },
  {
    "stt": 104,
    "base_form": "knit",
    "past_simple": "knit/knitted",
    "past_participle": "knit/knitted",
    "define": "đan"
  },
  {
    "stt": 105,
    "base_form": "know",
    "past_simple": "knew",
    "past_participle": "known",
    "define": "biết, quen biết"
  },
  {
    "stt": 106,
    "base_form": "lay",
    "past_simple": "laid",
    "past_participle": "laid",
    "define": "đặt, để"
  },
  {
    "stt": 107,
    "base_form": "lead",
    "past_simple": "led",
    "past_participle": "led",
    "define": "dẫn dắt, lãnh đạo"
  },
  {
    "stt": 108,
    "base_form": "lean",
    "past_simple": "leaned/leant",
    "past_participle": "leaned/leant",
    "define": "dựa, tựa"
  },
  {
    "stt": 109,
    "base_form": "leap",
    "past_simple": "leapt",
    "past_participle": "leapt",
    "define": "nhảy, nhảy qua"
  },
  {
    "stt": 110,
    "base_form": "learn",
    "past_simple": "learnt/learned",
    "past_participle": "learnt/learned",
    "define": "học, được biết"
  },
  {
    "stt": 111,
    "base_form": "leave",
    "past_simple": "left",
    "past_participle": "left",
    "define": "ra đi, để lại"
  },
  {
    "stt": 112,
    "base_form": "lend",
    "past_simple": "lent",
    "past_participle": "lent",
    "define": "cho mượn"
  },
  {
    "stt": 113,
    "base_form": "let",
    "past_simple": "let",
    "past_participle": "let",
    "define": "cho phép, để cho"
  },
  {
    "stt": 114,
    "base_form": "lie",
    "past_simple": "lay",
    "past_participle": "lain",
    "define": "nằm"
  },
  {
    "stt": 115,
    "base_form": "light",
    "past_simple": "lit/lighted",
    "past_participle": "lit/lighted",
    "define": "thắp sáng"
  },
  {
    "stt": 116,
    "base_form": "lip-read",
    "past_simple": "lip-read",
    "past_participle": "lip-read",
    "define": "mấp máy môi"
  },
  {
    "stt": 117,
    "base_form": "lose",
    "past_simple": "lost",
    "past_participle": "lost",
    "define": "làm mất, mất"
  },
  {
    "stt": 118,
    "base_form": "make",
    "past_simple": "made",
    "past_participle": "made",
    "define": "chế tạo, sản xuất"
  },
  {
    "stt": 119,
    "base_form": "mean",
    "past_simple": "meant",
    "past_participle": "meant",
    "define": "có nghĩa là"
  },
  {
    "stt": 120,
    "base_form": "meet",
    "past_simple": "met",
    "past_participle": "met",
    "define": "gặp mặt"
  },
  {
    "stt": 121,
    "base_form": "miscast",
    "past_simple": "miscast",
    "past_participle": "miscast",
    "define": "chọn vai đóng không hợp"
  },
  {
    "stt": 122,
    "base_form": "misdeal",
    "past_simple": "misdealt",
    "past_participle": "misdealt",
    "define": "chia lộn bài, chia bài sai"
  },
  {
    "stt": 123,
    "base_form": "misdo",
    "past_simple": "misdid",
    "past_participle": "misdone",
    "define": "phạm lỗi"
  },
  {
    "stt": 124,
    "base_form": "mishear",
    "past_simple": "misheard",
    "past_participle": "misheard",
    "define": "nghe nhầm"
  },
  {
    "stt": 125,
    "base_form": "mislay",
    "past_simple": "mislaid",
    "past_participle": "mislaid",
    "define": "để lạc mất"
  },
  {
    "stt": 126,
    "base_form": "mislead",
    "past_simple": "misled",
    "past_participle": "misled",
    "define": "làm lạc đường"
  },
  {
    "stt": 127,
    "base_form": "mislearn",
    "past_simple": "mislearned",
    "past_participle": "mislearned",
    "define": "học nhầm"
  },
  {
    "stt": "",
    "base_form": "",
    "past_simple": "mislearnt",
    "past_participle": "mislearnt",
    "define": ""
  },
  {
    "stt": 128,
    "base_form": "misread",
    "past_simple": "misread",
    "past_participle": "misread",
    "define": "đọc sai"
  },
  {
    "stt": 129,
    "base_form": "misset",
    "past_simple": "misset",
    "past_participle": "misset",
    "define": "đặt sai chỗ"
  },
  {
    "stt": 130,
    "base_form": "misspeak",
    "past_simple": "misspoke",
    "past_participle": "misspoken",
    "define": "nói sai"
  },
  {
    "stt": 131,
    "base_form": "misspell",
    "past_simple": "misspelt",
    "past_participle": "misspelt",
    "define": "viết sai chính tả"
  },
  {
    "stt": 132,
    "base_form": "misspend",
    "past_simple": "misspent",
    "past_participle": "misspent",
    "define": "tiêu phí, bỏ phí"
  },
  {
    "stt": 133,
    "base_form": "mistake",
    "past_simple": "mistook",
    "past_participle": "mistaken",
    "define": "lầm lẫn"
  },
  {
    "stt": 134,
    "base_form": "misteach",
    "past_simple": "mistaught",
    "past_participle": "mistaught",
    "define": "dạy sai"
  },
  {
    "stt": 135,
    "base_form": "misunderstand",
    "past_simple": "misunderstood",
    "past_participle": "misunderstood",
    "define": "hiểu lầm"
  },
  {
    "stt": 136,
    "base_form": "miswrite",
    "past_simple": "miswrote",
    "past_participle": "miswritten",
    "define": "viết sai"
  },
  {
    "stt": 137,
    "base_form": "mow",
    "past_simple": "mowed",
    "past_participle": "mown/mowed",
    "define": "cắt cỏ"
  },
  {
    "stt": 138,
    "base_form": "offset",
    "past_simple": "offset",
    "past_participle": "offset",
    "define": "đền bù"
  },
  {
    "stt": 139,
    "base_form": "outbid",
    "past_simple": "outbid",
    "past_participle": "outbid",
    "define": "trả hơn giá"
  },
  {
    "stt": 140,
    "base_form": "outbreed",
    "past_simple": "outbred",
    "past_participle": "outbred",
    "define": "giao phối xa"
  },
  {
    "stt": 141,
    "base_form": "outdo",
    "past_simple": "outdid",
    "past_participle": "outdone",
    "define": "làm giỏi hơn"
  },
  {
    "stt": 142,
    "base_form": "outdraw",
    "past_simple": "outdrew",
    "past_participle": "outdrawn",
    "define": "rút súng ra nhanh hơn"
  },
  {
    "stt": 143,
    "base_form": "outdrink",
    "past_simple": "outdrank",
    "past_participle": "outdrunk",
    "define": "uống quá chén"
  },
  {
    "stt": 144,
    "base_form": "outdrive",
    "past_simple": "outdrove",
    "past_participle": "outdriven",
    "define": "lái nhanh hơn"
  },
  {
    "stt": 145,
    "base_form": "outfight",
    "past_simple": "outfought",
    "past_participle": "outfought",
    "define": "đánh giỏi hơn"
  },
  {
    "stt": 146,
    "base_form": "outfly",
    "past_simple": "outflew",
    "past_participle": "outflown",
    "define": "bay cao/xa hơn"
  },
  {
    "stt": 147,
    "base_form": "outgrow",
    "past_simple": "outgrew",
    "past_participle": "outgrown",
    "define": "lớn nhanh hơn"
  },
  {
    "stt": 148,
    "base_form": "outleap",
    "past_simple": "outleaped/outleapt",
    "past_participle": "outleaped/outleapt",
    "define": "nhảy cao/xa hơn"
  },
  {
    "stt": 149,
    "base_form": "outlie",
    "past_simple": "outlied",
    "past_participle": "outlied",
    "define": "nói dối"
  },
  {
    "stt": 150,
    "base_form": "output",
    "past_simple": "output",
    "past_participle": "output",
    "define": "cho ra (dữ kiện)"
  },
  {
    "stt": 151,
    "base_form": "outride",
    "past_simple": "outrode",
    "past_participle": "outridden",
    "define": "cưỡi ngựa giỏi hơn"
  },
  {
    "stt": 152,
    "base_form": "outrun",
    "past_simple": "outran",
    "past_participle": "outrun",
    "define": "chạy nhanh hơn, vượt giá"
  },
  {
    "stt": 153,
    "base_form": "outsell",
    "past_simple": "outsold",
    "past_participle": "outsold",
    "define": "bán nhanh hơn"
  },
  {
    "stt": 154,
    "base_form": "outshine",
    "past_simple": "outshined/outshone",
    "past_participle": "outshined/outshone",
    "define": "sáng hơn, rạng rỡ hơn"
  },
  {
    "stt": 155,
    "base_form": "outshoot",
    "past_simple": "outshot",
    "past_participle": "outshot",
    "define": "bắn giỏi hơn, nảy mầm, mọc"
  },
  {
    "stt": 156,
    "base_form": "outsing",
    "past_simple": "outsang",
    "past_participle": "outsung",
    "define": "hát hay hơn"
  },
  {
    "stt": 157,
    "base_form": "outsit",
    "past_simple": "outsat",
    "past_participle": "outsat",
    "define": "ngồi lâu hơn"
  },
  {
    "stt": 158,
    "base_form": "outsleep",
    "past_simple": "outslept",
    "past_participle": "outslept",
    "define": "ngủ lâu/muộn hơn"
  },
  {
    "stt": 159,
    "base_form": "outsmell",
    "past_simple": "outsmelled/outsmelt",
    "past_participle": "outsmelled/outsmelt",
    "define": "khám phá, đánh hơi, sặc mùi"
  },
  {
    "stt": 160,
    "base_form": "outspeak",
    "past_simple": "outspoke",
    "past_participle": "outspoken",
    "define": "nói nhiều/dài/to hơn"
  },
  {
    "stt": 161,
    "base_form": "outspeed",
    "past_simple": "outsped",
    "past_participle": "outsped",
    "define": "đi/chạy nhanh hơn"
  },
  {
    "stt": 162,
    "base_form": "outspend",
    "past_simple": "outspent",
    "past_participle": "outspent",
    "define": "tiêu tiền nhiều hơn"
  },
  {
    "stt": 163,
    "base_form": "outswear",
    "past_simple": "outswore",
    "past_participle": "outsworn",
    "define": "nguyền rủa nhiều hơn"
  },
  {
    "stt": 164,
    "base_form": "outswim",
    "past_simple": "outswam",
    "past_participle": "outswum",
    "define": "bơi giỏi hơn"
  },
  {
    "stt": 165,
    "base_form": "outthink",
    "past_simple": "outthought",
    "past_participle": "outthought",
    "define": "suy nghĩ nhanh hơn"
  },
  {
    "stt": 166,
    "base_form": "outthrow",
    "past_simple": "outthrew",
    "past_participle": "outthrown",
    "define": "ném nhanh hơn"
  },
  {
    "stt": 167,
    "base_form": "outwrite",
    "past_simple": "outwrote",
    "past_participle": "outwritten",
    "define": "viết nhanh hơn"
  },
  {
    "stt": 168,
    "base_form": "overbid",
    "past_simple": "overbid",
    "past_participle": "overbid",
    "define": "trả giá/bỏ thầu cao hơn"
  },
  {
    "stt": 169,
    "base_form": "overbreed",
    "past_simple": "overbred",
    "past_participle": "overbred",
    "define": "nuôi quá nhiều"
  },
  {
    "stt": 170,
    "base_form": "overbuild",
    "past_simple": "overbuilt",
    "past_participle": "overbuilt",
    "define": "xây quá nhiều"
  },
  {
    "stt": 171,
    "base_form": "overbuy",
    "past_simple": "overbought",
    "past_participle": "overbought",
    "define": "mua quá nhiều"
  },
  {
    "stt": 172,
    "base_form": "overcome",
    "past_simple": "overcame",
    "past_participle": "overcome",
    "define": "khắc phục"
  },
  {
    "stt": 173,
    "base_form": "overdo",
    "past_simple": "overdid",
    "past_participle": "overdone",
    "define": "dùng quá mức, làm quá"
  },
  {
    "stt": 174,
    "base_form": "overdraw",
    "past_simple": "overdrew",
    "past_participle": "overdrawn",
    "define": "rút quá số tiền, phóng đại"
  },
  {
    "stt": 175,
    "base_form": "overdrink",
    "past_simple": "overdrank",
    "past_participle": "overdrunk",
    "define": "uống quá nhiều"
  },
  {
    "stt": 176,
    "base_form": "overeat",
    "past_simple": "overate",
    "past_participle": "overeaten",
    "define": "ăn quá nhiều"
  },
  {
    "stt": 177,
    "base_form": "overfeed",
    "past_simple": "overfed",
    "past_participle": "overfed",
    "define": "cho ăn quá mức"
  },
  {
    "stt": 178,
    "base_form": "overfly",
    "past_simple": "overflew",
    "past_participle": "overflown",
    "define": "bay qua"
  },
  {
    "stt": 179,
    "base_form": "overhang",
    "past_simple": "overhung",
    "past_participle": "overhung",
    "define": "nhô lên trên, treo lơ lửng"
  },
  {
    "stt": 180,
    "base_form": "overhear",
    "past_simple": "overheard",
    "past_participle": "overheard",
    "define": "nghe trộm"
  },
  {
    "stt": 181,
    "base_form": "overlay",
    "past_simple": "overlaid",
    "past_participle": "overlaid",
    "define": "phủ lên"
  },
  {
    "stt": 182,
    "base_form": "overpay",
    "past_simple": "overpaid",
    "past_participle": "overpaid",
    "define": "trả quá tiền"
  },
  {
    "stt": 183,
    "base_form": "override",
    "past_simple": "overrode",
    "past_participle": "overridden",
    "define": "lạm quyền"
  },
  {
    "stt": 184,
    "base_form": "overrun",
    "past_simple": "overran",
    "past_participle": "overrun",
    "define": "tràn ngập"
  },
  {
    "stt": 185,
    "base_form": "oversee",
    "past_simple": "oversaw",
    "past_participle": "overseen",
    "define": "trông nom"
  },
  {
    "stt": 186,
    "base_form": "oversell",
    "past_simple": "oversold",
    "past_participle": "oversold",
    "define": "bán quá mức"
  },
  {
    "stt": 187,
    "base_form": "oversew",
    "past_simple": "oversewed",
    "past_participle": "oversewn/oversewed",
    "define": "may nối vắt"
  },
  {
    "stt": 188,
    "base_form": "overshoot",
    "past_simple": "overshot",
    "past_participle": "overshot",
    "define": "đi quá đích"
  },
  {
    "stt": 189,
    "base_form": "oversleep",
    "past_simple": "overslept",
    "past_participle": "overslept",
    "define": "ngủ quên"
  },
  {
    "stt": 190,
    "base_form": "overspeak",
    "past_simple": "overspoke",
    "past_participle": "overspoken",
    "define": "Nói quá nhiều, nói lấn át"
  },
  {
    "stt": 191,
    "base_form": "overspend",
    "past_simple": "overspent",
    "past_participle": "overspent",
    "define": "tiêu quá lố"
  },
  {
    "stt": 192,
    "base_form": "overspill",
    "past_simple": "overspilled/overspilt",
    "past_participle": "overspilled/overspilt",
    "define": "đổ, làm tràn"
  },
  {
    "stt": 193,
    "base_form": "overtake",
    "past_simple": "overtook",
    "past_participle": "overtaken",
    "define": "đuổi bắt kịp"
  },
  {
    "stt": 194,
    "base_form": "overthink",
    "past_simple": "overthought",
    "past_participle": "overthought",
    "define": "tính trước nhiều quá"
  },
  {
    "stt": 195,
    "base_form": "overthrow",
    "past_simple": "overthrew",
    "past_participle": "overthrown",
    "define": "lật đổ"
  },
  {
    "stt": 196,
    "base_form": "overwind",
    "past_simple": "overwound",
    "past_participle": "overwound",
    "define": "lên dây (đồng hồ) quá chặt"
  },
  {
    "stt": 197,
    "base_form": "overwrite",
    "past_simple": "overwrote",
    "past_participle": "overwritten",
    "define": "viết dài quá, viết đè lên"
  },
  {
    "stt": 198,
    "base_form": "partake",
    "past_simple": "partook",
    "past_participle": "partaken",
    "define": "tham gia, dự phần"
  },
  {
    "stt": 199,
    "base_form": "pay",
    "past_simple": "paid",
    "past_participle": "paid",
    "define": "trả (tiền)"
  },
  {
    "stt": 200,
    "base_form": "plead",
    "past_simple": "pleaded/pled",
    "past_participle": "pleaded/pled",
    "define": "bào chữa, biện hộ"
  },
  {
    "stt": 201,
    "base_form": "prebuild",
    "past_simple": "prebuilt",
    "past_participle": "prebuilt",
    "define": "làm nhà tiền chế"
  },
  {
    "stt": 202,
    "base_form": "predo",
    "past_simple": "predid",
    "past_participle": "predone",
    "define": "làm trước"
  },
  {
    "stt": 203,
    "base_form": "premake",
    "past_simple": "premade",
    "past_participle": "premade",
    "define": "làm trước"
  },
  {
    "stt": 204,
    "base_form": "prepay",
    "past_simple": "prepaid",
    "past_participle": "prepaid",
    "define": "trả trước"
  },
  {
    "stt": 205,
    "base_form": "presell",
    "past_simple": "presold",
    "past_participle": "presold",
    "define": "bán trước thời gian rao báo"
  },
  {
    "stt": 206,
    "base_form": "preset",
    "past_simple": "preset",
    "past_participle": "preset",
    "define": "thiết lập sẵn, cài đặt sẵn"
  },
  {
    "stt": 207,
    "base_form": "preshrink",
    "past_simple": "preshrank",
    "past_participle": "preshrunk",
    "define": "ngâm cho vải co trước khi may"
  },
  {
    "stt": 208,
    "base_form": "proofread",
    "past_simple": "proofread",
    "past_participle": "proofread",
    "define": "đọc bản thảo trước khi in"
  },
  {
    "stt": 209,
    "base_form": "prove",
    "past_simple": "proved",
    "past_participle": "proven/proved",
    "define": "chứng minh"
  },
  {
    "stt": 210,
    "base_form": "put",
    "past_simple": "put",
    "past_participle": "put",
    "define": "đặt, để"
  },
  {
    "stt": 211,
    "base_form": "quick-freeze",
    "past_simple": "quick-froze",
    "past_participle": "quick-frozen",
    "define": "kết đông nhanh"
  },
  {
    "stt": 212,
    "base_form": "quit",
    "past_simple": "quit/quitted",
    "past_participle": "quit/quitted",
    "define": "bỏ"
  },
  {
    "stt": 213,
    "base_form": "read",
    "past_simple": "read",
    "past_participle": "read",
    "define": "đọc"
  },
  {
    "stt": 214,
    "base_form": "reawake",
    "past_simple": "reawoke",
    "past_participle": "reawaken",
    "define": "đánh thức 1 lần nữa"
  },
  {
    "stt": 215,
    "base_form": "rebid",
    "past_simple": "rebid",
    "past_participle": "rebid",
    "define": "trả giá, bỏ thầu"
  },
  {
    "stt": 216,
    "base_form": "rebind",
    "past_simple": "rebound",
    "past_participle": "rebound",
    "define": "buộc lại, đóng lại"
  },
  {
    "stt": 217,
    "base_form": "rebroadcast",
    "past_simple": "rebroadcast",
    "past_participle": "rebroadcast",
    "define": "cự tuyệt, khước từ"
  },
  {
    "stt": "",
    "base_form": "",
    "past_simple": "rebroadcasted",
    "past_participle": "rebroadcasted",
    "define": ""
  },
  {
    "stt": 218,
    "base_form": "rebuild",
    "past_simple": "rebuilt",
    "past_participle": "rebuilt",
    "define": "xây dựng lại"
  },
  {
    "stt": 219,
    "base_form": "recast",
    "past_simple": "recast",
    "past_participle": "recast",
    "define": "đúc lại"
  },
  {
    "stt": 220,
    "base_form": "recut",
    "past_simple": "recut",
    "past_participle": "recut",
    "define": "cắt lại, băm)"
  },
  {
    "stt": 221,
    "base_form": "redeal",
    "past_simple": "redealt",
    "past_participle": "redealt",
    "define": "phát bài lại"
  },
  {
    "stt": 222,
    "base_form": "redo",
    "past_simple": "redid",
    "past_participle": "redone",
    "define": "làm lại"
  },
  {
    "stt": 223,
    "base_form": "redraw",
    "past_simple": "redrew",
    "past_participle": "redrawn",
    "define": "kéo ngược lại"
  },
  {
    "stt": 224,
    "base_form": "refit",
    "past_simple": "refitted/refit",
    "past_participle": "refitted/refit",
    "define": "luồn, xỏ"
  },
  {
    "stt": 225,
    "base_form": "regrind",
    "past_simple": "reground",
    "past_participle": "reground",
    "define": "mài sắc lại"
  },
  {
    "stt": 226,
    "base_form": "regrow",
    "past_simple": "regrew",
    "past_participle": "regrown",
    "define": "trồng lại"
  },
  {
    "stt": 227,
    "base_form": "rehang",
    "past_simple": "rehung",
    "past_participle": "rehung",
    "define": "treo lại"
  },
  {
    "stt": 228,
    "base_form": "rehear",
    "past_simple": "reheard",
    "past_participle": "reheard",
    "define": "nghe trình bày lại"
  },
  {
    "stt": 229,
    "base_form": "reknit",
    "past_simple": "reknitted/reknit",
    "past_participle": "reknitted/reknit",
    "define": "đan lại"
  },
  {
    "stt": 230,
    "base_form": "relay",
    "past_simple": "relaid",
    "past_participle": "relaid",
    "define": "đặt lại"
  },
  {
    "stt": 231,
    "base_form": "relay",
    "past_simple": "relayed",
    "past_participle": "relayed",
    "define": "truyền âm lại"
  },
  {
    "stt": 232,
    "base_form": "relearn",
    "past_simple": "relearned/relearnt",
    "past_participle": "relearned/relearnt",
    "define": "học lại"
  },
  {
    "stt": 233,
    "base_form": "relight",
    "past_simple": "relit/relighted",
    "past_participle": "relit/relighted",
    "define": "thắp sáng lại"
  },
  {
    "stt": 234,
    "base_form": "remake",
    "past_simple": "remade",
    "past_participle": "remade",
    "define": "làm lại, chế tạo lại"
  },
  {
    "stt": 235,
    "base_form": "rend",
    "past_simple": "rent",
    "past_participle": "rent",
    "define": "toạc ra, xé"
  },
  {
    "stt": 236,
    "base_form": "repay",
    "past_simple": "repaid",
    "past_participle": "repaid",
    "define": "hoàn tiền lại"
  },
  {
    "stt": 237,
    "base_form": "reread",
    "past_simple": "reread",
    "past_participle": "reread",
    "define": "đọc lại"
  },
  {
    "stt": 238,
    "base_form": "rerun",
    "past_simple": "reran",
    "past_participle": "rerun",
    "define": "chiếu lại, phát lại"
  },
  {
    "stt": 239,
    "base_form": "resell",
    "past_simple": "resold",
    "past_participle": "resold",
    "define": "bán lại"
  },
  {
    "stt": 240,
    "base_form": "resend",
    "past_simple": "resent",
    "past_participle": "resent",
    "define": "gửi lại"
  },
  {
    "stt": 241,
    "base_form": "reset",
    "past_simple": "reset",
    "past_participle": "reset",
    "define": "đặt lại, lắp lại"
  },
  {
    "stt": 242,
    "base_form": "resew",
    "past_simple": "resewed",
    "past_participle": "resewn/resewed",
    "define": "may/khâu lại"
  },
  {
    "stt": 243,
    "base_form": "retake",
    "past_simple": "retook",
    "past_participle": "retaken",
    "define": "chiếm lại,tái chiếm"
  },
  {
    "stt": 244,
    "base_form": "reteach",
    "past_simple": "retaught",
    "past_participle": "retaught",
    "define": "dạy lại"
  },
  {
    "stt": 245,
    "base_form": "retear",
    "past_simple": "retore",
    "past_participle": "retorn",
    "define": "khóc lại"
  },
  {
    "stt": 246,
    "base_form": "retell",
    "past_simple": "retold",
    "past_participle": "retold",
    "define": "kể lại"
  },
  {
    "stt": 247,
    "base_form": "rethink",
    "past_simple": "rethought",
    "past_participle": "rethought",
    "define": "suy tính lại"
  },
  {
    "stt": 248,
    "base_form": "retread",
    "past_simple": "retread",
    "past_participle": "retread",
    "define": "lại giẫm/đạp lên"
  },
  {
    "stt": 249,
    "base_form": "retrofit",
    "past_simple": "retrofitted/retrofit",
    "past_participle": "retrofitted/retrofit",
    "define": "trang bị thêm những bộ phận mới"
  },
  {
    "stt": 250,
    "base_form": "rewake",
    "past_simple": "rewoke/rewaked",
    "past_participle": "rewaken/rewaked",
    "define": "đánh thức lại"
  },
  {
    "stt": 251,
    "base_form": "rewear",
    "past_simple": "rewore",
    "past_participle": "reworn",
    "define": "mặc lại"
  },
  {
    "stt": 252,
    "base_form": "reweave",
    "past_simple": "rewove/reweaved",
    "past_participle": "rewoven/reweaved",
    "define": "dệt lại"
  },
  {
    "stt": 253,
    "base_form": "rewed",
    "past_simple": "rewed/rewedded",
    "past_participle": "rewed/rewedded",
    "define": "tái hôn"
  },
  {
    "stt": 254,
    "base_form": "rewet",
    "past_simple": "rewet/rewetted",
    "past_participle": "rewet/rewetted",
    "define": "làm ướt lại"
  },
  {
    "stt": 255,
    "base_form": "rewin",
    "past_simple": "rewon",
    "past_participle": "rewon",
    "define": "thắng lại"
  },
  {
    "stt": 256,
    "base_form": "rewind",
    "past_simple": "rewound",
    "past_participle": "rewound",
    "define": "cuốn lại, lên dây lại"
  },
  {
    "stt": 257,
    "base_form": "rewrite",
    "past_simple": "rewrote",
    "past_participle": "rewritten",
    "define": "viết lại"
  },
  {
    "stt": 258,
    "base_form": "rid",
    "past_simple": "rid",
    "past_participle": "rid",
    "define": "giải thoát"
  },
  {
    "stt": 259,
    "base_form": "ride",
    "past_simple": "rode",
    "past_participle": "ridden",
    "define": "cưỡi"
  },
  {
    "stt": 260,
    "base_form": "ring",
    "past_simple": "rang",
    "past_participle": "rung",
    "define": "rung chuông"
  },
  {
    "stt": 261,
    "base_form": "rise",
    "past_simple": "rose",
    "past_participle": "risen",
    "define": "đứng dậy, mọc"
  },
  {
    "stt": 262,
    "base_form": "roughcast",
    "past_simple": "roughcast",
    "past_participle": "roughcast",
    "define": "tạo hình phỏng chừng"
  },
  {
    "stt": 263,
    "base_form": "run",
    "past_simple": "ran",
    "past_participle": "run",
    "define": "chạy"
  },
  {
    "stt": 264,
    "base_form": "sand-cast",
    "past_simple": "sand-cast",
    "past_participle": "sand-cast",
    "define": "đúc bằng khuôn cát"
  },
  {
    "stt": 265,
    "base_form": "saw",
    "past_simple": "sawed",
    "past_participle": "sawn",
    "define": "cưa"
  },
  {
    "stt": 266,
    "base_form": "say",
    "past_simple": "said",
    "past_participle": "said",
    "define": "nói"
  },
  {
    "stt": 267,
    "base_form": "see",
    "past_simple": "saw",
    "past_participle": "seen",
    "define": "nhìn thấy"
  },
  {
    "stt": 268,
    "base_form": "seek",
    "past_simple": "sought",
    "past_participle": "sought",
    "define": "tìm kiếm"
  },
  {
    "stt": 269,
    "base_form": "sell",
    "past_simple": "sold",
    "past_participle": "sold",
    "define": "bán"
  },
  {
    "stt": 270,
    "base_form": "send",
    "past_simple": "sent",
    "past_participle": "sent",
    "define": "gửi"
  },
  {
    "stt": 271,
    "base_form": "set",
    "past_simple": "set",
    "past_participle": "set",
    "define": "đặt, thiết lập"
  },
  {
    "stt": 272,
    "base_form": "sew",
    "past_simple": "sewed",
    "past_participle": "sewn/sewed",
    "define": "may"
  },
  {
    "stt": 273,
    "base_form": "shake",
    "past_simple": "shook",
    "past_participle": "shaken",
    "define": "lay, lắc"
  },
  {
    "stt": 274,
    "base_form": "shave",
    "past_simple": "shaved",
    "past_participle": "shaved/shaven",
    "define": "cạo (râu)"
  },
  {
    "stt": 275,
    "base_form": "shear",
    "past_simple": "sheared",
    "past_participle": "shorn",
    "define": "xén lông (cừu)"
  },
  {
    "stt": 276,
    "base_form": "shed",
    "past_simple": "shed",
    "past_participle": "shed",
    "define": "rơi, rụng"
  },
  {
    "stt": 277,
    "base_form": "shine",
    "past_simple": "shone",
    "past_participle": "shone",
    "define": "chiếu sáng"
  },
  {
    "stt": 278,
    "base_form": "shit",
    "past_simple": "shit/shat/shitted",
    "past_participle": "shit/shat/shitted",
    "define": "suộc khuộng đi đại tiện"
  },
  {
    "stt": 279,
    "base_form": "shoot",
    "past_simple": "shot",
    "past_participle": "shot",
    "define": "bắn"
  },
  {
    "stt": 280,
    "base_form": "show",
    "past_simple": "showed",
    "past_participle": "shown/showed",
    "define": "cho xem"
  },
  {
    "stt": 281,
    "base_form": "shrink",
    "past_simple": "shrank",
    "past_participle": "shrunk",
    "define": "co rút"
  },
  {
    "stt": 282,
    "base_form": "shut",
    "past_simple": "shut",
    "past_participle": "shut",
    "define": "đóng lại"
  },
  {
    "stt": 283,
    "base_form": "sight-read",
    "past_simple": "sight-read",
    "past_participle": "sight-read",
    "define": "chơi hoặc hát mà không cần nghiên cứu trước"
  },
  {
    "stt": 284,
    "base_form": "sing",
    "past_simple": "sang",
    "past_participle": "sung",
    "define": "ca hát"
  },
  {
    "stt": 285,
    "base_form": "sink",
    "past_simple": "sank",
    "past_participle": "sunk",
    "define": "chìm, lặn"
  },
  {
    "stt": 286,
    "base_form": "sit",
    "past_simple": "sat",
    "past_participle": "sat",
    "define": "ngồi"
  },
  {
    "stt": 287,
    "base_form": "slay",
    "past_simple": "slew",
    "past_participle": "slain",
    "define": "sát hại, giết hại"
  },
  {
    "stt": 288,
    "base_form": "sleep",
    "past_simple": "slept",
    "past_participle": "slept",
    "define": "ngủ"
  },
  {
    "stt": 289,
    "base_form": "slide",
    "past_simple": "slid",
    "past_participle": "slid",
    "define": "trượt, lướt"
  },
  {
    "stt": 290,
    "base_form": "sling",
    "past_simple": "slung",
    "past_participle": "slung",
    "define": "ném mạnh"
  },
  {
    "stt": 291,
    "base_form": "slink",
    "past_simple": "slunk",
    "past_participle": "slunk",
    "define": "lẻn đi"
  },
  {
    "stt": 292,
    "base_form": "slit",
    "past_simple": "slit",
    "past_participle": "slit",
    "define": "rạch, khứa"
  },
  {
    "stt": 293,
    "base_form": "smell",
    "past_simple": "smelt",
    "past_participle": "smelt",
    "define": "ngửi"
  },
  {
    "stt": 294,
    "base_form": "smite",
    "past_simple": "smote",
    "past_participle": "smitten",
    "define": "đập mạnh"
  },
  {
    "stt": 295,
    "base_form": "sneak",
    "past_simple": "sneaked/snuck",
    "past_participle": "sneaked/snuck",
    "define": "trốn, lén"
  },
  {
    "stt": 296,
    "base_form": "speak",
    "past_simple": "spoke",
    "past_participle": "spoken",
    "define": "nói"
  },
  {
    "stt": 298,
    "base_form": "speed",
    "past_simple": "sped/speeded",
    "past_participle": "sped/speeded",
    "define": "chạy vụt"
  },
  {
    "stt": 299,
    "base_form": "spell",
    "past_simple": "spelt/spelled",
    "past_participle": "spelt/spelled",
    "define": "đánh vần"
  },
  {
    "stt": 300,
    "base_form": "spend",
    "past_simple": "spent",
    "past_participle": "spent",
    "define": "tiêu xài"
  },
  {
    "stt": 301,
    "base_form": "spill",
    "past_simple": "spilt/spilled",
    "past_participle": "spilt/spilled",
    "define": "tràn, đổ ra"
  },
  {
    "stt": 302,
    "base_form": "spin",
    "past_simple": "spun/span",
    "past_participle": "spun",
    "define": "quay sợi"
  },
  {
    "stt": 303,
    "base_form": "spoil",
    "past_simple": "spoilt/spoiled",
    "past_participle": "spoilt/spoiled",
    "define": "làm hỏng"
  },
  {
    "stt": 304,
    "base_form": "spread",
    "past_simple": "spread",
    "past_participle": "spread",
    "define": "lan truyền"
  },
  {
    "stt": 305,
    "base_form": "stand",
    "past_simple": "stood",
    "past_participle": "stood",
    "define": "đứng"
  },
  {
    "stt": 305,
    "base_form": "steal",
    "past_simple": "stole",
    "past_participle": "stolen",
    "define": "đánh cắp"
  },
  {
    "stt": 306,
    "base_form": "stick",
    "past_simple": "stuck",
    "past_participle": "stuck",
    "define": "ghim vào, đính"
  },
  {
    "stt": 307,
    "base_form": "sting",
    "past_simple": "stung",
    "past_participle": "stung",
    "define": "châm, chích, đốt"
  },
  {
    "stt": 308,
    "base_form": "stink",
    "past_simple": "stunk/stank",
    "past_participle": "stunk",
    "define": "bốc mùi hôi"
  },
  {
    "stt": 309,
    "base_form": "stride",
    "past_simple": "strode",
    "past_participle": "stridden",
    "define": "bước sải"
  },
  {
    "stt": 310,
    "base_form": "strike",
    "past_simple": "struck",
    "past_participle": "struck",
    "define": "đánh đập"
  },
  {
    "stt": 311,
    "base_form": "string",
    "past_simple": "strung",
    "past_participle": "strung",
    "define": "gắn dây vào"
  },
  {
    "stt": 312,
    "base_form": "sunburn",
    "past_simple": "sunburned/sunburnt",
    "past_participle": "sunburned/sunburnt",
    "define": "cháy nắng"
  },
  {
    "stt": 313,
    "base_form": "swear",
    "past_simple": "swore",
    "past_participle": "sworn",
    "define": "tuyên thệ"
  },
  {
    "stt": 314,
    "base_form": "sweat",
    "past_simple": "sweat/sweated",
    "past_participle": "sweat/sweated",
    "define": "đổ mồ hôi"
  },
  {
    "stt": 315,
    "base_form": "sweep",
    "past_simple": "swept",
    "past_participle": "swept",
    "define": "quét"
  },
  {
    "stt": 316,
    "base_form": "swell",
    "past_simple": "swelled",
    "past_participle": "swollen/swelled",
    "define": "phồng, sưng"
  },
  {
    "stt": 317,
    "base_form": "swim",
    "past_simple": "swam",
    "past_participle": "swum",
    "define": "bơi lội"
  },
  {
    "stt": 318,
    "base_form": "swing",
    "past_simple": "swung",
    "past_participle": "swung",
    "define": "đong đưa"
  },
  {
    "stt": 319,
    "base_form": "take",
    "past_simple": "took",
    "past_participle": "taken",
    "define": "cầm, lấy"
  },
  {
    "stt": 320,
    "base_form": "teach",
    "past_simple": "taught",
    "past_participle": "taught",
    "define": "dạy, giảng dạy"
  },
  {
    "stt": 321,
    "base_form": "tear",
    "past_simple": "tore",
    "past_participle": "torn",
    "define": "xé, rách"
  },
  {
    "stt": 322,
    "base_form": "telecast",
    "past_simple": "telecast",
    "past_participle": "telecast",
    "define": "phát đi bằng truyền hình"
  },
  {
    "stt": 323,
    "base_form": "tell",
    "past_simple": "told",
    "past_participle": "told",
    "define": "kể, bảo"
  },
  {
    "stt": 324,
    "base_form": "think",
    "past_simple": "thought",
    "past_participle": "thought",
    "define": "suy nghĩ"
  },
  {
    "stt": 325,
    "base_form": "throw",
    "past_simple": "threw",
    "past_participle": "thrown",
    "define": "ném,, liệng"
  },
  {
    "stt": 326,
    "base_form": "thrust",
    "past_simple": "thrust",
    "past_participle": "thrust",
    "define": "thọc, nhấn"
  },
  {
    "stt": 327,
    "base_form": "tread",
    "past_simple": "trod",
    "past_participle": "trodden/trod",
    "define": "giẫm, đạp"
  },
  {
    "stt": 328,
    "base_form": "typewrite",
    "past_simple": "typewrote",
    "past_participle": "typewritten",
    "define": "đánh máy"
  },
  {
    "stt": 329,
    "base_form": "unbend",
    "past_simple": "unbent",
    "past_participle": "unbent",
    "define": "làm thẳng lại"
  },
  {
    "stt": 330,
    "base_form": "unbind",
    "past_simple": "unbound",
    "past_participle": "unbound",
    "define": "mở, tháo ra"
  },
  {
    "stt": 331,
    "base_form": "unclothe",
    "past_simple": "unclothed/unclad",
    "past_participle": "unclothed/unclad",
    "define": "cởi áo, lột trần"
  },
  {
    "stt": 332,
    "base_form": "undercut",
    "past_simple": "undercut",
    "past_participle": "undercut",
    "define": "ra giá rẻ hơn"
  },
  {
    "stt": 333,
    "base_form": "underfeed",
    "past_simple": "underfed",
    "past_participle": "underfed",
    "define": "cho ăn đói, thiếu ăn"
  },
  {
    "stt": 334,
    "base_form": "undergo",
    "past_simple": "underwent",
    "past_participle": "undergone",
    "define": "kinh qua"
  },
  {
    "stt": 335,
    "base_form": "underlie",
    "past_simple": "underlay",
    "past_participle": "underlain",
    "define": "nằm dưới"
  },
  {
    "stt": 336,
    "base_form": "understand",
    "past_simple": "understood",
    "past_participle": "understood",
    "define": "hiểu"
  },
  {
    "stt": 337,
    "base_form": "undertake",
    "past_simple": "undertook",
    "past_participle": "undertaken",
    "define": "đảm nhận"
  },
  {
    "stt": 338,
    "base_form": "underwrite",
    "past_simple": "underwrote",
    "past_participle": "underwritten",
    "define": "bảo hiểm"
  },
  {
    "stt": 339,
    "base_form": "undo",
    "past_simple": "undid",
    "past_participle": "undone",
    "define": "tháo ra"
  },
  {
    "stt": 340,
    "base_form": "unfreeze",
    "past_simple": "unfroze",
    "past_participle": "unfrozen",
    "define": "làm tan đông"
  },
  {
    "stt": 341,
    "base_form": "unhang",
    "past_simple": "unhung",
    "past_participle": "unhung",
    "define": "hạ xuống, bỏ xuống"
  },
  {
    "stt": 342,
    "base_form": "unhide",
    "past_simple": "unhid",
    "past_participle": "unhidden",
    "define": "hiển thị, không ẩn"
  },
  {
    "stt": 343,
    "base_form": "unlearn",
    "past_simple": "unlearned/unlearnt",
    "past_participle": "unlearned/unlearnt",
    "define": "gạt bỏ, quên"
  },
  {
    "stt": 344,
    "base_form": "unspin",
    "past_simple": "unspun",
    "past_participle": "unspun",
    "define": "quay ngược"
  },
  {
    "stt": 345,
    "base_form": "unwind",
    "past_simple": "unwound",
    "past_participle": "unwound",
    "define": "tháo ra"
  },
  {
    "stt": 346,
    "base_form": "uphold",
    "past_simple": "upheld",
    "past_participle": "upheld",
    "define": "ủng hộ"
  },
  {
    "stt": 347,
    "base_form": "upset",
    "past_simple": "upset",
    "past_participle": "upset",
    "define": "đánh đổ, lật đổ"
  },
  {
    "stt": 348,
    "base_form": "wake",
    "past_simple": "woke/waked",
    "past_participle": "woken/waked",
    "define": "thức giấc"
  },
  {
    "stt": 349,
    "base_form": "wear",
    "past_simple": "wore",
    "past_participle": "worn",
    "define": "mặc"
  },
  {
    "stt": 350,
    "base_form": "wed",
    "past_simple": "wed/wedded",
    "past_participle": "wed/wedded",
    "define": "kết hôn"
  },
  {
    "stt": 351,
    "base_form": "weep",
    "past_simple": "wept",
    "past_participle": "wept",
    "define": "khóc"
  },
  {
    "stt": 352,
    "base_form": "wet",
    "past_simple": "wet/wetted",
    "past_participle": "wet/wetted",
    "define": "làm ướt"
  },
  {
    "stt": 353,
    "base_form": "win",
    "past_simple": "won",
    "past_participle": "won",
    "define": "chiến thắng"
  },
  {
    "stt": 354,
    "base_form": "wind",
    "past_simple": "wound",
    "past_participle": "wound",
    "define": "quấn"
  },
  {
    "stt": 355,
    "base_form": "withdraw",
    "past_simple": "withdrew",
    "past_participle": "withdrawn",
    "define": "rút lui"
  },
  {
    "stt": 356,
    "base_form": "withhold",
    "past_simple": "withheld",
    "past_participle": "withheld",
    "define": "khước từ"
  },
  {
    "stt": 357,
    "base_form": "withstand",
    "past_simple": "withstood",
    "past_participle": "withstood",
    "define": "cầm cự"
  },
  {
    "stt": 358,
    "base_form": "work",
    "past_simple": "worked",
    "past_participle": "worked",
    "define": "rèn, nhào nặn đất"
  },
  {
    "stt": 359,
    "base_form": "wring",
    "past_simple": "wrung",
    "past_participle": "wrung",
    "define": "vặn, siết chặt"
  },
  {
    "stt": 360,
    "base_form": "write",
    "past_simple": "wrote",
    "past_participle": "written",
    "define": "viết"
  }
]
// initialize components based on data attribute selectors
onMounted(() => {
    initFlowbite();
})
</script>

<template>
    <div class="relative top-0 left-1/2 -translate-x-1/2 bg-white max-w-[768px] w-full h-screen">
        <div class="w-full shadow-xl h-full">
            <img class="w-full h-[157px]" src="@/assets/images/profile/banner.png" />
            <div class="bg-white rounded-tl-[20px] rounded-tr-[20px] -mt-6 relative z-[1]">
                <div class="flex flex-col gap-2 items-center justify-center relative -top-10">
                    <img class="w-20 h-20 rounded-full" src="@/assets/images/profile/avatar.png" />
                    <div class="text-neutral-900 text-[22px] font-normal leading-snug">Giant Boy</div>
                    <div class="text-justify text-neutral-400 text-sm font-normal leading-snug">no pain no gain</div>
                </div>
                <div class="flex items-center justify-around">
                    <div>
                        <div class="cursor-pointer w-[102px] h-[102px] p-[15px] bg-violet-100 border-2 border-transparent hover:border-violet-600 rounded-[5px] shadow justify-start items-center gap-2.5 inline-flex">
                            <div class="justify-center items-center">
                                <img class="w-[72px] h-[72px] select-none" src="@/assets/images/profile/words.png" />
                            </div>
                        </div>
                        <div class="mt-2 text-center">360 words</div>
                    </div>
                    <div>
                        <div class="cursor-pointer w-[102px] h-[102px] p-[15px] bg-sky-100 border-2 border-transparent hover:border-sky-600 rounded-[5px] shadow justify-start items-center gap-2.5 inline-flex">
                            <div class="justify-center items-center">
                                <img class="w-[72px] h-[72px] select-none" src="@/assets/images/profile/exercise.png" />
                            </div>
                        </div>
                        <div class="mt-2 text-center">exercise</div>
                    </div>
                </div>
                <div class="cursor-pointer w-ful max-w-[294px] h-[53px] mx-auto mt-10 p-[18px] bg-rose-100 hover:bg-rose-200 rounded-[10px] border-2 border-rose-100 hover:border-rose-600 block">
                    <div class="font-bold text-center text-red-400 hover:text-red-600 text-sm uppercase">START</div>
                </div>
            </div>
        </div>
         <!-- footer -->
        <div class="fixed left-0 bottom-0 w-full border-t-2 border-gray-200">
            <div class="flex items-center justify-around h-20">
                <div class="cursor-pointer w-1/2 flex justify-center">
                    <svg width="25" height="24" viewBox="0 0 25 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <g clip-path="url(#clip0_2_64)">
                    <path d="M23.2787 9.88345L23.2793 9.88395C23.4514 10.0324 23.5625 10.2532 23.5625 10.5V22.5C23.5625 22.9486 23.1986 23.3125 22.75 23.3125H1.75C1.30143 23.3125 0.9375 22.9486 0.9375 22.5V10.5C0.9375 10.2539 1.04737 10.0325 1.2213 9.88345L1.384 10.0733L1.2213 9.88345L11.7213 0.883449L11.7214 0.883506M23.2787 9.88345L11.7214 0.883506M23.2787 9.88345L12.7792 0.88386C12.7791 0.883791 12.779 0.883722 12.7789 0.883653C12.6373 0.761701 12.4516 0.688263 12.25 0.688263C12.0487 0.688263 11.8635 0.761464 11.7214 0.883506M23.2787 9.88345L11.7214 0.883506M9.3125 21.6875V18C9.3125 16.3778 10.6278 15.0625 12.25 15.0625C13.8722 15.0625 15.1875 16.3778 15.1875 18V21.6875H9.3125ZM21.9375 21.6875H16.8125V18C16.8125 15.4799 14.7701 13.4375 12.25 13.4375C9.72993 13.4375 7.6875 15.4799 7.6875 18V21.6875H2.5625V10.8738L12.25 2.57102L21.9375 10.8738V21.6875Z" fill="#B1B1B1" stroke="#B1B1B1" stroke-width="0.5"/>
                    </g>
                    <defs>
                    <clipPath id="clip0_2_64">
                    <rect width="24" height="24" fill="white" transform="translate(0.25)"/>
                    </clipPath>
                    </defs>
                    </svg>
                </div>
                <div class="cursor-pointer w-1/2 flex justify-center">
                    <svg width="25" height="24" viewBox="0 0 25 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <g clip-path="url(#clip0_2_69)">
                    <path d="M12.7497 12.8125H12.75C16.0981 12.8125 18.8125 10.0981 18.8125 6.75C18.8125 3.40193 16.0981 0.6875 12.75 0.6875C9.40193 0.6875 6.6875 3.40193 6.6875 6.75V6.75029C6.69141 10.0966 9.40336 12.8086 12.7497 12.8125ZM23.1882 23.2928L23.1882 23.2927C23.5104 23.2189 23.7588 22.9578 23.8114 22.63H23.8639L23.8093 22.3566C23.8071 22.3447 23.8047 22.3328 23.8021 22.321L23.8006 22.3214C22.647 17.2049 18.1393 13.4375 12.75 13.4375C7.36037 13.4375 2.85104 17.2057 1.71288 22.2507L1.71275 22.2507L1.71123 22.2586L1.69772 22.329C1.68558 22.3839 1.67975 22.4423 1.67975 22.5C1.67975 22.9486 2.04368 23.3125 2.49225 23.3125C2.87955 23.3125 3.2032 23.0413 3.28446 22.6784L3.28452 22.6784L3.28565 22.6728L3.2858 22.672C4.27519 18.2857 8.13738 15.0625 12.75 15.0625C17.3632 15.0625 21.2244 18.2868 22.202 22.6051L22.2139 22.6677L22.2138 22.6677L22.2155 22.6753C22.2972 23.0409 22.6192 23.3132 23.0085 23.3132H23.0092C23.0726 23.3132 23.1325 23.3055 23.1882 23.2928ZM12.7502 2.3125C15.201 2.3126 17.1875 4.29913 17.1875 6.75C17.1875 9.20093 15.2009 11.1875 12.75 11.1875C10.2992 11.1875 8.31266 9.20109 8.3125 6.75029C8.31534 4.30067 10.3006 2.3154 12.7502 2.3125Z" fill="#E67052" stroke="#E67052" stroke-width="0.5"/>
                    </g>
                    <defs>
                    <clipPath id="clip0_2_69">
                    <rect width="24" height="24" fill="white" transform="translate(0.75)"/>
                    </clipPath>
                    </defs>
                    </svg>
                </div>
            </div>
        </div>
    </div>
</template>