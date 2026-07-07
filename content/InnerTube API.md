### Caption
```js
const tracks = data?.captions?.playerCaptionsTracklistRender?.captionTracks;

selectTrack(tracks);
```

```json
{
    "captions": {
      "playerCaptionsTracklistRender": {
        "captionTracks": [
          {
            "baseUrl": "https://*.com/...",
            "name": {
              "simpleText": "English"
            },
            "vssId": ".en",
            "isTranslatable": "true",
            "trackName": ""
          },
          {
            "...": "..."
          }
    ]
      }
    }
}
```

### JSON (접기)
```json
{
  "responseContext": {
    "visitorData": "Cgt6N0t6c2xESTJCQSjE-eHKBjIKCgJLUhIEGgAgKg%3D%3D",
    "serviceTrackingParams": [
      {
        "service": "GFEEDBACK",
        "params": [
          {
            "key": "is_viewed_live",
            "value": "False"
          },
          {
            "key": "ipcc",
            "value": "0"
          },
          {
            "key": "is_alc_surface",
            "value": "false"
          },
          {
            "key": "logged_in",
            "value": "0"
          },
          {
            "key": "visitor_data",
            "value": "Cgt6N0t6c2xESTJCQSjE-eHKBjIKCgJLUhIEGgAgKg%3D%3D"
          }
        ]
      },
      {
        "service": "CSI",
        "params": [
          {
            "key": "yt_ad",
            "value": "1"
          },
          {
            "key": "c",
            "value": "WEB"
          },
          {
            "key": "cver",
            "value": "2.20240201"
          },
          {
            "key": "yt_li",
            "value": "0"
          },
          {
            "key": "GetPlayer_rid",
            "value": "0xd6d65261879d282a"
          }
        ]
      },
      {
        "service": "GUIDED_HELP",
        "params": [
          {
            "key": "logged_in",
            "value": "0"
          }
        ]
      },
      {
        "service": "ECATCHER",
        "params": [
          {
            "key": "client.version",
            "value": "2.20250331"
          },
          {
            "key": "client.name",
            "value": "WEB"
          }
        ]
      }
    ],
    "maxAgeSeconds": 0,
    "mainAppWebResponseContext": {
      "loggedOut": true,
      "trackingParam": "kx_fmPxhoPZR62BRn0JdraQLOwydrGQ3TDsVOjkuQUombqzRgkuMsNLBwOcCE59TDtslLKPQ-SS"
    },
    "webResponseContextExtensionData": {
      "webResponseContextPreloadData": {
        "preloadMessageNames": [
          "miniplayerRenderer",
          "playerCaptionsTracklistRenderer",
          "playerAnnotationsExpandedRenderer",
          "subscribeButtonRenderer",
          "confirmDialogRenderer",
          "buttonRenderer",
          "playerStoryboardSpecRenderer",
          "playerMicroformatRenderer",
          "cardCollectionRenderer",
          "cardRenderer",
          "simpleCardTeaserRenderer",
          "infoCardIconRenderer",
          "mealbarPromoRenderer"
        ]
      },
      "hasDecorated": true
    }
  },
  "playabilityStatus": {
    "status": "OK",
    "playableInEmbed": true,
    "miniplayer": {
      "miniplayerRenderer": {
        "playbackMode": "PLAYBACK_MODE_ALLOW"
      }
    },
    "contextParams": "Q0FFU0FnZ0M="
  },
  "streamingData": {
    "expiresInSeconds": "21540",
    "formats": [
      {
        "itag": 18,
        "url": "https://rr3---sn-ab02a0nfpgxapox-bh266.googlevideo.com/videoplayback?expire=1767428388&ei=xHxYadbtJZLg1d8Pvrnx0A0&ip=210.107.70.86&id=o-AN5ekoLfvWz7As_Vo7eD3sIhP_mmLbQ_QYEsvLE5yWmI&itag=18&source=youtube&requiressl=yes&xpc=EgVo2aDSNQ%3D%3D&cps=657&met=1767406788%2C&mh=Og&mm=31%2C26&mn=sn-ab02a0nfpgxapox-bh266%2Csn-un57snee&ms=au%2Conr&mv=m&mvi=3&pl=17&rms=au%2Cau&initcwndbps=4300000&bui=AYUSA3CW3uiuEWtNW0exwUn4hoJaYV1SBPM3HNqkba8YieGV3NCh-WnTJ0NCG2t5hB8pzYpGdfCA4nPr&spc=wH4Qq5WVf_YBeP5dbadhEZIur43xneJXHJiu62UAqZCfgvSPAJd0v6jy8jXgO14w5kuMqA&vprv=1&svpuc=1&mime=video%2Fmp4&ns=TkEV5tiZyBxO5-iHUOzocfYR&rqh=1&gir=yes&clen=136147973&ratebypass=yes&dur=2918.864&lmt=1767371711400671&mt=1767406180&fvip=3&fexp=51355912%2C51552689%2C51565115%2C51565682%2C51580968&c=WEB&sefc=1&txp=4538534&n=tPSqfejZjVLkRA4T&sparams=expire%2Cei%2Cip%2Cid%2Citag%2Csource%2Crequiressl%2Cxpc%2Cbui%2Cspc%2Cvprv%2Csvpuc%2Cmime%2Cns%2Crqh%2Cgir%2Cclen%2Cratebypass%2Cdur%2Clmt&sig=AJfQdSswRAIgeZPaNBVJDvNfWZ7Ax0wdnlCb6T44sS9yKl-FYKg2Es8CIBSUeoF769234aasEnEQrSiJGOD4O7eYQIEhf2V014Su&lsparams=cps%2Cmet%2Cmh%2Cmm%2Cmn%2Cms%2Cmv%2Cmvi%2Cpl%2Crms%2Cinitcwndbps&lsig=APaTxxMwRgIhAIIlZjMuJ4lJ7aWSOXWfYbPUNiFxZBhsUTRG3Oq--RuBAiEAqrVqUfSPvGLVB4y8LT1CiRwVKnieenI6gtaDRuzjIns%3D",
        "mimeType": "video/mp4; codecs=\"avc1.42001E, mp4a.40.2\"",
        "bitrate": 373159,
        "width": 640,
        "height": 360,
        "lastModified": "1767371711400671",
        "contentLength": "136147973",
        "quality": "medium",
        "fps": 30,
        "qualityLabel": "360p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 373153,
        "audioQuality": "AUDIO_QUALITY_LOW",
        "approxDurationMs": "2918864",
        "audioSampleRate": "44100",
        "audioChannels": 2,
        "qualityOrdinal": "QUALITY_ORDINAL_360P"
      }
    ],
    "adaptiveFormats": [
      {
        "itag": 137,
        "mimeType": "video/mp4; codecs=\"avc1.640028\"",
        "bitrate": 4327228,
        "width": 1920,
        "height": 1080,
        "initRange": {
          "start": "0",
          "end": "740"
        },
        "indexRange": {
          "start": "741",
          "end": "7648"
        },
        "lastModified": "1767373646870637",
        "contentLength": "347108622",
        "quality": "hd1080",
        "fps": 30,
        "qualityLabel": "1080p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 951368,
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_1080P"
      },
      {
        "itag": 248,
        "mimeType": "video/webm; codecs=\"vp9\"",
        "bitrate": 2946160,
        "width": 1920,
        "height": 1080,
        "initRange": {
          "start": "0",
          "end": "220"
        },
        "indexRange": {
          "start": "221",
          "end": "10501"
        },
        "lastModified": "1767381837362880",
        "contentLength": "300634792",
        "quality": "hd1080",
        "fps": 30,
        "qualityLabel": "1080p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 823991,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918816",
        "qualityOrdinal": "QUALITY_ORDINAL_1080P"
      },
      {
        "itag": 399,
        "mimeType": "video/mp4; codecs=\"av01.0.08M.08\"",
        "bitrate": 2587781,
        "width": 1920,
        "height": 1080,
        "initRange": {
          "start": "0",
          "end": "699"
        },
        "indexRange": {
          "start": "700",
          "end": "7607"
        },
        "lastModified": "1767375258603194",
        "contentLength": "196425644",
        "quality": "hd1080",
        "fps": 30,
        "qualityLabel": "1080p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 538370,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_1080P"
      },
      {
        "itag": 136,
        "mimeType": "video/mp4; codecs=\"avc1.4d401f\"",
        "bitrate": 1376037,
        "width": 1280,
        "height": 720,
        "initRange": {
          "start": "0",
          "end": "738"
        },
        "indexRange": {
          "start": "739",
          "end": "7646"
        },
        "lastModified": "1767373389329934",
        "contentLength": "82512476",
        "quality": "hd720",
        "fps": 30,
        "qualityLabel": "720p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 226153,
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_720P"
      },
      {
        "itag": 247,
        "mimeType": "video/webm; codecs=\"vp9\"",
        "bitrate": 1317970,
        "width": 1280,
        "height": 720,
        "initRange": {
          "start": "0",
          "end": "219"
        },
        "indexRange": {
          "start": "220",
          "end": "10481"
        },
        "lastModified": "1767380675185203",
        "contentLength": "158735220",
        "quality": "hd720",
        "fps": 30,
        "qualityLabel": "720p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 435067,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918816",
        "qualityOrdinal": "QUALITY_ORDINAL_720P"
      },
      {
        "itag": 398,
        "mimeType": "video/mp4; codecs=\"av01.0.05M.08\"",
        "bitrate": 1207959,
        "width": 1280,
        "height": 720,
        "initRange": {
          "start": "0",
          "end": "699"
        },
        "indexRange": {
          "start": "700",
          "end": "7607"
        },
        "lastModified": "1767372403861000",
        "contentLength": "107373480",
        "quality": "hd720",
        "fps": 30,
        "qualityLabel": "720p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 294293,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_720P"
      },
      {
        "itag": 135,
        "mimeType": "video/mp4; codecs=\"avc1.4d401f\"",
        "bitrate": 731449,
        "width": 854,
        "height": 480,
        "initRange": {
          "start": "0",
          "end": "738"
        },
        "indexRange": {
          "start": "739",
          "end": "7646"
        },
        "lastModified": "1767375589044592",
        "contentLength": "45282218",
        "quality": "large",
        "fps": 30,
        "qualityLabel": "480p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 124111,
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_480P"
      },
      {
        "itag": 244,
        "mimeType": "video/webm; codecs=\"vp9\"",
        "bitrate": 611632,
        "width": 854,
        "height": 480,
        "initRange": {
          "start": "0",
          "end": "219"
        },
        "indexRange": {
          "start": "220",
          "end": "10430"
        },
        "lastModified": "1767384367009272",
        "contentLength": "89111661",
        "quality": "large",
        "fps": 30,
        "qualityLabel": "480p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 244240,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918816",
        "qualityOrdinal": "QUALITY_ORDINAL_480P"
      },
      {
        "itag": 397,
        "mimeType": "video/mp4; codecs=\"av01.0.04M.08\"",
        "bitrate": 672460,
        "width": 854,
        "height": 480,
        "initRange": {
          "start": "0",
          "end": "699"
        },
        "indexRange": {
          "start": "700",
          "end": "7607"
        },
        "lastModified": "1767372227623637",
        "contentLength": "61010530",
        "quality": "large",
        "fps": 30,
        "qualityLabel": "480p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 167219,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_480P"
      },
      {
        "itag": 134,
        "mimeType": "video/mp4; codecs=\"avc1.4d401e\"",
        "bitrate": 460225,
        "width": 640,
        "height": 360,
        "initRange": {
          "start": "0",
          "end": "738"
        },
        "indexRange": {
          "start": "739",
          "end": "7646"
        },
        "lastModified": "1767375322958706",
        "contentLength": "30731000",
        "quality": "medium",
        "fps": 30,
        "qualityLabel": "360p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 84228,
        "highReplication": true,
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_360P"
      },
      {
        "itag": 243,
        "mimeType": "video/webm; codecs=\"vp9\"",
        "bitrate": 387479,
        "width": 640,
        "height": 360,
        "initRange": {
          "start": "0",
          "end": "219"
        },
        "indexRange": {
          "start": "220",
          "end": "10389"
        },
        "lastModified": "1767378879723909",
        "contentLength": "65586496",
        "quality": "medium",
        "fps": 30,
        "qualityLabel": "360p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 179761,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918816",
        "qualityOrdinal": "QUALITY_ORDINAL_360P"
      },
      {
        "itag": 396,
        "mimeType": "video/mp4; codecs=\"av01.0.01M.08\"",
        "bitrate": 317900,
        "width": 640,
        "height": 360,
        "initRange": {
          "start": "0",
          "end": "699"
        },
        "indexRange": {
          "start": "700",
          "end": "7607"
        },
        "lastModified": "1767371689997809",
        "contentLength": "36866176",
        "quality": "medium",
        "fps": 30,
        "qualityLabel": "360p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 101044,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_360P"
      },
      {
        "itag": 133,
        "mimeType": "video/mp4; codecs=\"avc1.4d4015\"",
        "bitrate": 200270,
        "width": 426,
        "height": 240,
        "initRange": {
          "start": "0",
          "end": "738"
        },
        "indexRange": {
          "start": "739",
          "end": "7646"
        },
        "lastModified": "1767377519775737",
        "contentLength": "17582523",
        "quality": "small",
        "fps": 30,
        "qualityLabel": "240p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 48190,
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_240P"
      },
      {
        "itag": 242,
        "mimeType": "video/webm; codecs=\"vp9\"",
        "bitrate": 172360,
        "width": 426,
        "height": 240,
        "initRange": {
          "start": "0",
          "end": "218"
        },
        "indexRange": {
          "start": "219",
          "end": "10211"
        },
        "lastModified": "1767385629898927",
        "contentLength": "32155710",
        "quality": "small",
        "fps": 30,
        "qualityLabel": "240p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 88133,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918816",
        "qualityOrdinal": "QUALITY_ORDINAL_240P"
      },
      {
        "itag": 395,
        "mimeType": "video/mp4; codecs=\"av01.0.00M.08\"",
        "bitrate": 139657,
        "width": 426,
        "height": 240,
        "initRange": {
          "start": "0",
          "end": "699"
        },
        "indexRange": {
          "start": "700",
          "end": "7607"
        },
        "lastModified": "1767370524659639",
        "contentLength": "20558425",
        "quality": "small",
        "fps": 30,
        "qualityLabel": "240p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 56347,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_240P"
      },
      {
        "itag": 160,
        "mimeType": "video/mp4; codecs=\"avc1.4d400c\"",
        "bitrate": 104754,
        "width": 256,
        "height": 144,
        "initRange": {
          "start": "0",
          "end": "737"
        },
        "indexRange": {
          "start": "738",
          "end": "7645"
        },
        "lastModified": "1767378427569118",
        "contentLength": "11442637",
        "quality": "tiny",
        "fps": 30,
        "qualityLabel": "144p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 31362,
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_144P"
      },
      {
        "itag": 278,
        "mimeType": "video/webm; codecs=\"vp9\"",
        "bitrate": 96222,
        "width": 256,
        "height": 144,
        "initRange": {
          "start": "0",
          "end": "218"
        },
        "indexRange": {
          "start": "219",
          "end": "10058"
        },
        "lastModified": "1767379724737056",
        "contentLength": "21014133",
        "quality": "tiny",
        "fps": 30,
        "qualityLabel": "144p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 57596,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918816",
        "qualityOrdinal": "QUALITY_ORDINAL_144P"
      },
      {
        "itag": 394,
        "mimeType": "video/mp4; codecs=\"av01.0.00M.08\"",
        "bitrate": 78202,
        "width": 256,
        "height": 144,
        "initRange": {
          "start": "0",
          "end": "699"
        },
        "indexRange": {
          "start": "700",
          "end": "7607"
        },
        "lastModified": "1767370632751250",
        "contentLength": "16087535",
        "quality": "tiny",
        "fps": 30,
        "qualityLabel": "144p",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 44093,
        "colorInfo": {
          "primaries": "COLOR_PRIMARIES_BT709",
          "transferCharacteristics": "COLOR_TRANSFER_CHARACTERISTICS_BT709",
          "matrixCoefficients": "COLOR_MATRIX_COEFFICIENTS_BT709"
        },
        "approxDurationMs": "2918815",
        "qualityOrdinal": "QUALITY_ORDINAL_144P"
      },
      {
        "itag": 140,
        "mimeType": "audio/mp4; codecs=\"mp4a.40.2\"",
        "bitrate": 133187,
        "initRange": {
          "start": "0",
          "end": "722"
        },
        "indexRange": {
          "start": "723",
          "end": "4270"
        },
        "lastModified": "1767369055130614",
        "contentLength": "47239717",
        "quality": "tiny",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 129474,
        "highReplication": true,
        "audioQuality": "AUDIO_QUALITY_MEDIUM",
        "approxDurationMs": "2918864",
        "audioSampleRate": "44100",
        "audioChannels": 2,
        "loudnessDb": -3.0599995,
        "trackAbsoluteLoudnessLkfs": -17.06,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 140,
        "mimeType": "audio/mp4; codecs=\"mp4a.40.2\"",
        "bitrate": 133193,
        "initRange": {
          "start": "0",
          "end": "722"
        },
        "indexRange": {
          "start": "723",
          "end": "4270"
        },
        "lastModified": "1767371569753505",
        "contentLength": "47239730",
        "quality": "tiny",
        "xtags": "CggKA2RyYxIBMQ",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 129474,
        "highReplication": true,
        "audioQuality": "AUDIO_QUALITY_MEDIUM",
        "approxDurationMs": "2918864",
        "audioSampleRate": "44100",
        "audioChannels": 2,
        "loudnessDb": -3.459999,
        "isDrc": true,
        "trackAbsoluteLoudnessLkfs": -17.46,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 140,
        "mimeType": "audio/mp4; codecs=\"mp4a.40.2\"",
        "bitrate": 133205,
        "initRange": {
          "start": "0",
          "end": "722"
        },
        "indexRange": {
          "start": "723",
          "end": "4270"
        },
        "lastModified": "1767357928606932",
        "contentLength": "47239760",
        "quality": "tiny",
        "xtags": "CgcKAnZiEgEx",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 129474,
        "highReplication": true,
        "audioQuality": "AUDIO_QUALITY_MEDIUM",
        "approxDurationMs": "2918864",
        "audioSampleRate": "44100",
        "audioChannels": 2,
        "loudnessDb": 0.47000027,
        "trackAbsoluteLoudnessLkfs": -13.53,
        "isVb": true,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 249,
        "mimeType": "audio/webm; codecs=\"opus\"",
        "bitrate": 58252,
        "initRange": {
          "start": "0",
          "end": "265"
        },
        "indexRange": {
          "start": "266",
          "end": "5251"
        },
        "lastModified": "1767370357311666",
        "contentLength": "18380320",
        "quality": "tiny",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 50377,
        "audioQuality": "AUDIO_QUALITY_LOW",
        "approxDurationMs": "2918841",
        "audioSampleRate": "48000",
        "audioChannels": 2,
        "loudnessDb": -3.0599995,
        "trackAbsoluteLoudnessLkfs": -17.06,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 249,
        "mimeType": "audio/webm; codecs=\"opus\"",
        "bitrate": 58180,
        "initRange": {
          "start": "0",
          "end": "265"
        },
        "indexRange": {
          "start": "266",
          "end": "5252"
        },
        "lastModified": "1767371596207222",
        "contentLength": "18430385",
        "quality": "tiny",
        "xtags": "CggKA2RyYxIBMQ",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 50514,
        "audioQuality": "AUDIO_QUALITY_LOW",
        "approxDurationMs": "2918841",
        "audioSampleRate": "48000",
        "audioChannels": 2,
        "loudnessDb": -3.459999,
        "isDrc": true,
        "trackAbsoluteLoudnessLkfs": -17.46,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 249,
        "mimeType": "audio/webm; codecs=\"opus\"",
        "bitrate": 55540,
        "initRange": {
          "start": "0",
          "end": "258"
        },
        "indexRange": {
          "start": "259",
          "end": "5244"
        },
        "lastModified": "1767357993501310",
        "contentLength": "18326603",
        "quality": "tiny",
        "xtags": "CgcKAnZiEgEx",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 50229,
        "audioQuality": "AUDIO_QUALITY_LOW",
        "approxDurationMs": "2918841",
        "audioSampleRate": "48000",
        "audioChannels": 2,
        "loudnessDb": 0.47000027,
        "trackAbsoluteLoudnessLkfs": -13.53,
        "isVb": true,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 250,
        "mimeType": "audio/webm; codecs=\"opus\"",
        "bitrate": 75532,
        "initRange": {
          "start": "0",
          "end": "265"
        },
        "indexRange": {
          "start": "266",
          "end": "5296"
        },
        "lastModified": "1767370407358297",
        "contentLength": "22055603",
        "quality": "tiny",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 60450,
        "audioQuality": "AUDIO_QUALITY_LOW",
        "approxDurationMs": "2918841",
        "audioSampleRate": "48000",
        "audioChannels": 2,
        "loudnessDb": -3.0599995,
        "trackAbsoluteLoudnessLkfs": -17.06,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 250,
        "mimeType": "audio/webm; codecs=\"opus\"",
        "bitrate": 75579,
        "initRange": {
          "start": "0",
          "end": "265"
        },
        "indexRange": {
          "start": "266",
          "end": "5297"
        },
        "lastModified": "1767371601406188",
        "contentLength": "22140498",
        "quality": "tiny",
        "xtags": "CggKA2RyYxIBMQ",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 60682,
        "audioQuality": "AUDIO_QUALITY_LOW",
        "approxDurationMs": "2918841",
        "audioSampleRate": "48000",
        "audioChannels": 2,
        "loudnessDb": -3.459999,
        "isDrc": true,
        "trackAbsoluteLoudnessLkfs": -17.46,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 250,
        "mimeType": "audio/webm; codecs=\"opus\"",
        "bitrate": 72523,
        "initRange": {
          "start": "0",
          "end": "258"
        },
        "indexRange": {
          "start": "259",
          "end": "5287"
        },
        "lastModified": "1767357994090891",
        "contentLength": "21828143",
        "quality": "tiny",
        "xtags": "CgcKAnZiEgEx",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 59826,
        "audioQuality": "AUDIO_QUALITY_LOW",
        "approxDurationMs": "2918841",
        "audioSampleRate": "48000",
        "audioChannels": 2,
        "loudnessDb": 0.47000027,
        "trackAbsoluteLoudnessLkfs": -13.53,
        "isVb": true,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 251,
        "mimeType": "audio/webm; codecs=\"opus\"",
        "bitrate": 148224,
        "initRange": {
          "start": "0",
          "end": "265"
        },
        "indexRange": {
          "start": "266",
          "end": "5401"
        },
        "lastModified": "1767370453086883",
        "contentLength": "41880994",
        "quality": "tiny",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 114788,
        "audioQuality": "AUDIO_QUALITY_MEDIUM",
        "approxDurationMs": "2918841",
        "audioSampleRate": "48000",
        "audioChannels": 2,
        "loudnessDb": -3.0599995,
        "trackAbsoluteLoudnessLkfs": -17.06,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 251,
        "mimeType": "audio/webm; codecs=\"opus\"",
        "bitrate": 148872,
        "initRange": {
          "start": "0",
          "end": "265"
        },
        "indexRange": {
          "start": "266",
          "end": "5401"
        },
        "lastModified": "1767371583625187",
        "contentLength": "42025681",
        "quality": "tiny",
        "xtags": "CggKA2RyYxIBMQ",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 115184,
        "audioQuality": "AUDIO_QUALITY_MEDIUM",
        "approxDurationMs": "2918841",
        "audioSampleRate": "48000",
        "audioChannels": 2,
        "loudnessDb": -3.459999,
        "isDrc": true,
        "trackAbsoluteLoudnessLkfs": -17.46,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      },
      {
        "itag": 251,
        "mimeType": "audio/webm; codecs=\"opus\"",
        "bitrate": 140123,
        "initRange": {
          "start": "0",
          "end": "258"
        },
        "indexRange": {
          "start": "259",
          "end": "5396"
        },
        "lastModified": "1767357993690827",
        "contentLength": "42783735",
        "quality": "tiny",
        "xtags": "CgcKAnZiEgEx",
        "projectionType": "RECTANGULAR",
        "averageBitrate": 117262,
        "audioQuality": "AUDIO_QUALITY_MEDIUM",
        "approxDurationMs": "2918841",
        "audioSampleRate": "48000",
        "audioChannels": 2,
        "loudnessDb": 0.47000027,
        "trackAbsoluteLoudnessLkfs": -13.53,
        "isVb": true,
        "qualityOrdinal": "QUALITY_ORDINAL_UNKNOWN"
      }
    ],
    "probeUrl": "https://r4---sn-ab02a0nfpgxapox-bh2lr.googlevideo.com/videogoodput?id=o-ADhSoR5_4RaxKO1joDsTjQkLIaBEb7dH12KGOe8nZ4Ug&source=goodput&range=0-4999&expire=1767410388&ip=210.107.70.86&ms=pm&mm=35&pl=24&sparams=id,source,range,expire,ip,ms,mm,pl&signature=25E0D327B4E7E8262852591E067A76F93E8CC9DB.81A4167A6FAC8CB3B184E3E134EF5D44307C9519&key=cms1",
    "serverAbrStreamingUrl": "https://rr3---sn-ab02a0nfpgxapox-bh266.googlevideo.com/videoplayback?expire=1767428388&ei=xHxYadbtJZLg1d8Pvrnx0A0&ip=210.107.70.86&id=o-AN5ekoLfvWz7As_Vo7eD3sIhP_mmLbQ_QYEsvLE5yWmI&source=youtube&requiressl=yes&xpc=EgVo2aDSNQ%3D%3D&cps=657&met=1767406788%2C&mh=Og&mm=31%2C26&mn=sn-ab02a0nfpgxapox-bh266%2Csn-un57snee&ms=au%2Conr&mv=m&mvi=3&pl=17&rms=au%2Cau&initcwndbps=4300000&spc=wH4Qq5WWf_YBeP5dbadhEZIur43wneJXHJiu62UAqZCfgvSPAJd0v6jy8jXgC1vY5tM&svpuc=1&ns=VrG1sY1Q7SH1DJ9t_jDgd40R&sabr=1&rqh=1&mt=1767406180&fvip=3&keepalive=yes&fexp=51355912%2C51552689%2C51565115%2C51565682%2C51580968&c=WEB&n=hQS--PJI5f1d7kS2&sparams=expire%2Cei%2Cip%2Cid%2Csource%2Crequiressl%2Cxpc%2Cspc%2Csvpuc%2Cns%2Csabr%2Crqh&sig=AJfQdSswRAIgEzIBeRCyhxmVbLP92teXF6A2y3EsEodvAGAKo1Lw6QECICSQVicQ1rSC6pfdYTYbHSQRt2fS9qn1LTuRpjMk9ric&lsparams=cps%2Cmet%2Cmh%2Cmm%2Cmn%2Cms%2Cmv%2Cmvi%2Cpl%2Crms%2Cinitcwndbps&lsig=APaTxxMwRgIhAIIlZjMuJ4lJ7aWSOXWfYbPUNiFxZBhsUTRG3Oq--RuBAiEAqrVqUfSPvGLVB4y8LT1CiRwVKnieenI6gtaDRuzjIns%3D"
  },
  "playbackTracking": {
    "videostatsPlaybackUrl": {
      "baseUrl": "https://s.youtube.com/api/stats/playback?cl=847500619&docid=mbtQAqqoHt0&ei=xHxYadbtJZLg1d8Pvrnx0A0&fexp=&ns=yt&plid=AAZHcnXPbYvJA71L&el=detailpage&len=2919&of=YaA-WI5EElhee6fVSBVACA&vm=CAEQARgEOjJBSHFpSlRLTm56eFpPd3FKamZmOHduZDUzcXM2T2FTQTdWTzNvaVpGOTcyblAtOEZuQWJYQUJFVEpNbTV4VzdUc2NLWmNHNkZDMFE5QVFFaFBUM1FxVGFndHRjVDBuSU9UTGR3TFhKU1dpQlpKV2xGUEs5ZEItUFlmY3R6ZkhBN1JNdEN5SGJTNVJuag"
    },
    "videostatsDelayplayUrl": {
      "baseUrl": "https://s.youtube.com/api/stats/delayplay?cl=847500619&docid=mbtQAqqoHt0&ei=xHxYadbtJZLg1d8Pvrnx0A0&fexp=&ns=yt&plid=AAZHcnXPbYvJA71L&el=detailpage&len=2919&of=YaA-WI5EElhee6fVSBVACA&vm=CAEQARgEOjJBSHFpSlRLTm56eFpPd3FKamZmOHduZDUzcXM2T2FTQTdWTzNvaVpGOTcyblAtOEZuQWJYQUJFVEpNbTV4VzdUc2NLWmNHNkZDMFE5QVFFaFBUM1FxVGFndHRjVDBuSU9UTGR3TFhKU1dpQlpKV2xGUEs5ZEItUFlmY3R6ZkhBN1JNdEN5SGJTNVJuag"
    },
    "videostatsWatchtimeUrl": {
      "baseUrl": "https://s.youtube.com/api/stats/watchtime?cl=847500619&docid=mbtQAqqoHt0&ei=xHxYadbtJZLg1d8Pvrnx0A0&fexp=&ns=yt&plid=AAZHcnXPbYvJA71L&el=detailpage&len=2919&of=YaA-WI5EElhee6fVSBVACA&vm=CAEQARgEOjJBSHFpSlRLTm56eFpPd3FKamZmOHduZDUzcXM2T2FTQTdWTzNvaVpGOTcyblAtOEZuQWJYQUJFVEpNbTV4VzdUc2NLWmNHNkZDMFE5QVFFaFBUM1FxVGFndHRjVDBuSU9UTGR3TFhKU1dpQlpKV2xGUEs5ZEItUFlmY3R6ZkhBN1JNdEN5SGJTNVJuag"
    },
    "ptrackingUrl": {
      "baseUrl": "https://www.youtube.com/ptracking?ei=xHxYadbtJZLg1d8Pvrnx0A0&oid=DqqiEGtVcyLMIocnDuJHoA&plid=AAZHcnXPbYvJA71L&pltype=content&ptchn=y-6oZwPwrR_W-zYnqLD8dg&ptk=youtube_single&video_id=mbtQAqqoHt0"
    },
    "qoeUrl": {
      "baseUrl": "https://s.youtube.com/api/stats/qoe?cl=847500619&docid=mbtQAqqoHt0&ei=xHxYadbtJZLg1d8Pvrnx0A0&el=detailpage&event=streamingstats&fexp=&ns=yt&plid=AAZHcnXPbYvJA71L&stmp=vb%3A1"
    },
    "atrUrl": {
      "baseUrl": "https://s.youtube.com/api/stats/atr?c=WEB&docid=mbtQAqqoHt0&ei=xHxYadbtJZLg1d8Pvrnx0A0&len=2919&ns=yt&plid=AAZHcnXPbYvJA71L&ver=2&vm=CAEQARgEOjJBSHFpSlRLTm56eFpPd3FKamZmOHduZDUzcXM2T2FTQTdWTzNvaVpGOTcyblAtOEZuQWJYQUJFVEpNbTV4VzdUc2NLWmNHNkZDMFE5QVFFaFBUM1FxVGFndHRjVDBuSU9UTGR3TFhKU1dpQlpKV2xGUEs5ZEItUFlmY3R6ZkhBN1JNdEN5SGJTNVJuag",
      "elapsedMediaTimeSeconds": 5
    },
    "videostatsScheduledFlushWalltimeSeconds": [
      10,
      20,
      30
    ],
    "videostatsDefaultFlushIntervalSeconds": 40,
    "youtubeRemarketingUrl": {
      "baseUrl": "https://www.youtube.com/pagead/viewthroughconversion/962985656/?backend=innertube&cname=1&cver=2_20250331&foc_id=y-6oZwPwrR_W-zYnqLD8dg&label=followon_view&ptype=no_rmkt&random=250315639",
      "elapsedMediaTimeSeconds": 0
    }
  },
  "captions": {
    "playerCaptionsTracklistRenderer": {
      "captionTracks": [
        {
          "baseUrl": "https://www.youtube.com/api/timedtext?v=mbtQAqqoHt0&ei=xHxYadbtJZLg1d8Pvrnx0A0&caps=asr&opi=112496729&xoaf=5&xowf=1&xospf=1&hl=en&ip=0.0.0.0&ipbits=0&expire=1767431988&sparams=ip,ipbits,expire,v,ei,caps,opi,xoaf&signature=ED44EBFF7B66B2B82CCC93EC6D28249F3CE0BCD7.8ADB489585EC32025E85C0A00D395F8F9EB0D615&key=yt8&kind=asr&lang=ko&variant=ec",
          "name": {
            "simpleText": "Korean (auto-generated)"
          },
          "vssId": "a.ko",
          "languageCode": "ko",
          "kind": "asr",
          "isTranslatable": true,
          "trackName": ""
        }
      ],
      "audioTracks": [
        {
          "captionTrackIndices": [
            0
          ]
        }
      ],
      "translationLanguages": [
        {
          "languageCode": "ab",
          "languageName": {
            "simpleText": "Abkhazian"
          }
        },
        {
          "languageCode": "aa",
          "languageName": {
            "simpleText": "Afar"
          }
        },
        {
          "languageCode": "af",
          "languageName": {
            "simpleText": "Afrikaans"
          }
        },
        {
          "languageCode": "ak",
          "languageName": {
            "simpleText": "Akan"
          }
        },
        {
          "languageCode": "sq",
          "languageName": {
            "simpleText": "Albanian"
          }
        },
        {
          "languageCode": "am",
          "languageName": {
            "simpleText": "Amharic"
          }
        },
        {
          "languageCode": "ar",
          "languageName": {
            "simpleText": "Arabic"
          }
        },
        {
          "languageCode": "hy",
          "languageName": {
            "simpleText": "Armenian"
          }
        },
        {
          "languageCode": "as",
          "languageName": {
            "simpleText": "Assamese"
          }
        },
        {
          "languageCode": "ay",
          "languageName": {
            "simpleText": "Aymara"
          }
        },
        {
          "languageCode": "az",
          "languageName": {
            "simpleText": "Azerbaijani"
          }
        },
        {
          "languageCode": "bn",
          "languageName": {
            "simpleText": "Bangla"
          }
        },
        {
          "languageCode": "ba",
          "languageName": {
            "simpleText": "Bashkir"
          }
        },
        {
          "languageCode": "eu",
          "languageName": {
            "simpleText": "Basque"
          }
        },
        {
          "languageCode": "be",
          "languageName": {
            "simpleText": "Belarusian"
          }
        },
        {
          "languageCode": "bho",
          "languageName": {
            "simpleText": "Bhojpuri"
          }
        },
        {
          "languageCode": "bs",
          "languageName": {
            "simpleText": "Bosnian"
          }
        },
        {
          "languageCode": "br",
          "languageName": {
            "simpleText": "Breton"
          }
        },
        {
          "languageCode": "bg",
          "languageName": {
            "simpleText": "Bulgarian"
          }
        },
        {
          "languageCode": "my",
          "languageName": {
            "simpleText": "Burmese"
          }
        },
        {
          "languageCode": "ca",
          "languageName": {
            "simpleText": "Catalan"
          }
        },
        {
          "languageCode": "ceb",
          "languageName": {
            "simpleText": "Cebuano"
          }
        },
        {
          "languageCode": "zh-Hans",
          "languageName": {
            "simpleText": "Chinese (Simplified)"
          }
        },
        {
          "languageCode": "zh-Hant",
          "languageName": {
            "simpleText": "Chinese (Traditional)"
          }
        },
        {
          "languageCode": "co",
          "languageName": {
            "simpleText": "Corsican"
          }
        },
        {
          "languageCode": "hr",
          "languageName": {
            "simpleText": "Croatian"
          }
        },
        {
          "languageCode": "cs",
          "languageName": {
            "simpleText": "Czech"
          }
        },
        {
          "languageCode": "da",
          "languageName": {
            "simpleText": "Danish"
          }
        },
        {
          "languageCode": "dv",
          "languageName": {
            "simpleText": "Divehi"
          }
        },
        {
          "languageCode": "nl",
          "languageName": {
            "simpleText": "Dutch"
          }
        },
        {
          "languageCode": "dz",
          "languageName": {
            "simpleText": "Dzongkha"
          }
        },
        {
          "languageCode": "en",
          "languageName": {
            "simpleText": "English"
          }
        },
        {
          "languageCode": "eo",
          "languageName": {
            "simpleText": "Esperanto"
          }
        },
        {
          "languageCode": "et",
          "languageName": {
            "simpleText": "Estonian"
          }
        },
        {
          "languageCode": "ee",
          "languageName": {
            "simpleText": "Ewe"
          }
        },
        {
          "languageCode": "fo",
          "languageName": {
            "simpleText": "Faroese"
          }
        },
        {
          "languageCode": "fj",
          "languageName": {
            "simpleText": "Fijian"
          }
        },
        {
          "languageCode": "fil",
          "languageName": {
            "simpleText": "Filipino"
          }
        },
        {
          "languageCode": "fi",
          "languageName": {
            "simpleText": "Finnish"
          }
        },
        {
          "languageCode": "fr",
          "languageName": {
            "simpleText": "French"
          }
        },
        {
          "languageCode": "gaa",
          "languageName": {
            "simpleText": "Ga"
          }
        },
        {
          "languageCode": "gl",
          "languageName": {
            "simpleText": "Galician"
          }
        },
        {
          "languageCode": "lg",
          "languageName": {
            "simpleText": "Ganda"
          }
        },
        {
          "languageCode": "ka",
          "languageName": {
            "simpleText": "Georgian"
          }
        },
        {
          "languageCode": "de",
          "languageName": {
            "simpleText": "German"
          }
        },
        {
          "languageCode": "el",
          "languageName": {
            "simpleText": "Greek"
          }
        },
        {
          "languageCode": "gn",
          "languageName": {
            "simpleText": "Guarani"
          }
        },
        {
          "languageCode": "gu",
          "languageName": {
            "simpleText": "Gujarati"
          }
        },
        {
          "languageCode": "ht",
          "languageName": {
            "simpleText": "Haitian Creole"
          }
        },
        {
          "languageCode": "ha",
          "languageName": {
            "simpleText": "Hausa"
          }
        },
        {
          "languageCode": "haw",
          "languageName": {
            "simpleText": "Hawaiian"
          }
        },
        {
          "languageCode": "iw",
          "languageName": {
            "simpleText": "Hebrew"
          }
        },
        {
          "languageCode": "hi",
          "languageName": {
            "simpleText": "Hindi"
          }
        },
        {
          "languageCode": "hmn",
          "languageName": {
            "simpleText": "Hmong"
          }
        },
        {
          "languageCode": "hu",
          "languageName": {
            "simpleText": "Hungarian"
          }
        },
        {
          "languageCode": "is",
          "languageName": {
            "simpleText": "Icelandic"
          }
        },
        {
          "languageCode": "ig",
          "languageName": {
            "simpleText": "Igbo"
          }
        },
        {
          "languageCode": "id",
          "languageName": {
            "simpleText": "Indonesian"
          }
        },
        {
          "languageCode": "iu",
          "languageName": {
            "simpleText": "Inuktitut"
          }
        },
        {
          "languageCode": "ga",
          "languageName": {
            "simpleText": "Irish"
          }
        },
        {
          "languageCode": "it",
          "languageName": {
            "simpleText": "Italian"
          }
        },
        {
          "languageCode": "ja",
          "languageName": {
            "simpleText": "Japanese"
          }
        },
        {
          "languageCode": "jv",
          "languageName": {
            "simpleText": "Javanese"
          }
        },
        {
          "languageCode": "kl",
          "languageName": {
            "simpleText": "Kalaallisut"
          }
        },
        {
          "languageCode": "kn",
          "languageName": {
            "simpleText": "Kannada"
          }
        },
        {
          "languageCode": "kk",
          "languageName": {
            "simpleText": "Kazakh"
          }
        },
        {
          "languageCode": "kha",
          "languageName": {
            "simpleText": "Khasi"
          }
        },
        {
          "languageCode": "km",
          "languageName": {
            "simpleText": "Khmer"
          }
        },
        {
          "languageCode": "rw",
          "languageName": {
            "simpleText": "Kinyarwanda"
          }
        },
        {
          "languageCode": "ko",
          "languageName": {
            "simpleText": "Korean"
          }
        },
        {
          "languageCode": "kri",
          "languageName": {
            "simpleText": "Krio"
          }
        },
        {
          "languageCode": "ku",
          "languageName": {
            "simpleText": "Kurdish"
          }
        },
        {
          "languageCode": "ky",
          "languageName": {
            "simpleText": "Kyrgyz"
          }
        },
        {
          "languageCode": "lo",
          "languageName": {
            "simpleText": "Lao"
          }
        },
        {
          "languageCode": "la",
          "languageName": {
            "simpleText": "Latin"
          }
        },
        {
          "languageCode": "lv",
          "languageName": {
            "simpleText": "Latvian"
          }
        },
        {
          "languageCode": "ln",
          "languageName": {
            "simpleText": "Lingala"
          }
        },
        {
          "languageCode": "lt",
          "languageName": {
            "simpleText": "Lithuanian"
          }
        },
        {
          "languageCode": "lua",
          "languageName": {
            "simpleText": "Luba-Lulua"
          }
        },
        {
          "languageCode": "luo",
          "languageName": {
            "simpleText": "Luo"
          }
        },
        {
          "languageCode": "lb",
          "languageName": {
            "simpleText": "Luxembourgish"
          }
        },
        {
          "languageCode": "mk",
          "languageName": {
            "simpleText": "Macedonian"
          }
        },
        {
          "languageCode": "mg",
          "languageName": {
            "simpleText": "Malagasy"
          }
        },
        {
          "languageCode": "ms",
          "languageName": {
            "simpleText": "Malay"
          }
        },
        {
          "languageCode": "ml",
          "languageName": {
            "simpleText": "Malayalam"
          }
        },
        {
          "languageCode": "mt",
          "languageName": {
            "simpleText": "Maltese"
          }
        },
        {
          "languageCode": "gv",
          "languageName": {
            "simpleText": "Manx"
          }
        },
        {
          "languageCode": "mi",
          "languageName": {
            "simpleText": "Māori"
          }
        },
        {
          "languageCode": "mr",
          "languageName": {
            "simpleText": "Marathi"
          }
        },
        {
          "languageCode": "mn",
          "languageName": {
            "simpleText": "Mongolian"
          }
        },
        {
          "languageCode": "mfe",
          "languageName": {
            "simpleText": "Morisyen"
          }
        },
        {
          "languageCode": "ne",
          "languageName": {
            "simpleText": "Nepali"
          }
        },
        {
          "languageCode": "new",
          "languageName": {
            "simpleText": "Newari"
          }
        },
        {
          "languageCode": "nso",
          "languageName": {
            "simpleText": "Northern Sotho"
          }
        },
        {
          "languageCode": "no",
          "languageName": {
            "simpleText": "Norwegian"
          }
        },
        {
          "languageCode": "ny",
          "languageName": {
            "simpleText": "Nyanja"
          }
        },
        {
          "languageCode": "oc",
          "languageName": {
            "simpleText": "Occitan"
          }
        },
        {
          "languageCode": "or",
          "languageName": {
            "simpleText": "Odia"
          }
        },
        {
          "languageCode": "om",
          "languageName": {
            "simpleText": "Oromo"
          }
        },
        {
          "languageCode": "os",
          "languageName": {
            "simpleText": "Ossetic"
          }
        },
        {
          "languageCode": "pam",
          "languageName": {
            "simpleText": "Pampanga"
          }
        },
        {
          "languageCode": "ps",
          "languageName": {
            "simpleText": "Pashto"
          }
        },
        {
          "languageCode": "fa",
          "languageName": {
            "simpleText": "Persian"
          }
        },
        {
          "languageCode": "pl",
          "languageName": {
            "simpleText": "Polish"
          }
        },
        {
          "languageCode": "pt",
          "languageName": {
            "simpleText": "Portuguese"
          }
        },
        {
          "languageCode": "pt-PT",
          "languageName": {
            "simpleText": "Portuguese (Portugal)"
          }
        },
        {
          "languageCode": "pa",
          "languageName": {
            "simpleText": "Punjabi"
          }
        },
        {
          "languageCode": "qu",
          "languageName": {
            "simpleText": "Quechua"
          }
        },
        {
          "languageCode": "ro",
          "languageName": {
            "simpleText": "Romanian"
          }
        },
        {
          "languageCode": "rn",
          "languageName": {
            "simpleText": "Rundi"
          }
        },
        {
          "languageCode": "ru",
          "languageName": {
            "simpleText": "Russian"
          }
        },
        {
          "languageCode": "sm",
          "languageName": {
            "simpleText": "Samoan"
          }
        },
        {
          "languageCode": "sg",
          "languageName": {
            "simpleText": "Sango"
          }
        },
        {
          "languageCode": "sa",
          "languageName": {
            "simpleText": "Sanskrit"
          }
        },
        {
          "languageCode": "gd",
          "languageName": {
            "simpleText": "Scottish Gaelic"
          }
        },
        {
          "languageCode": "sr",
          "languageName": {
            "simpleText": "Serbian"
          }
        },
        {
          "languageCode": "crs",
          "languageName": {
            "simpleText": "Seselwa Creole French"
          }
        },
        {
          "languageCode": "sn",
          "languageName": {
            "simpleText": "Shona"
          }
        },
        {
          "languageCode": "sd",
          "languageName": {
            "simpleText": "Sindhi"
          }
        },
        {
          "languageCode": "si",
          "languageName": {
            "simpleText": "Sinhala"
          }
        },
        {
          "languageCode": "sk",
          "languageName": {
            "simpleText": "Slovak"
          }
        },
        {
          "languageCode": "sl",
          "languageName": {
            "simpleText": "Slovenian"
          }
        },
        {
          "languageCode": "so",
          "languageName": {
            "simpleText": "Somali"
          }
        },
        {
          "languageCode": "st",
          "languageName": {
            "simpleText": "Southern Sotho"
          }
        },
        {
          "languageCode": "es",
          "languageName": {
            "simpleText": "Spanish"
          }
        },
        {
          "languageCode": "su",
          "languageName": {
            "simpleText": "Sundanese"
          }
        },
        {
          "languageCode": "sw",
          "languageName": {
            "simpleText": "Swahili"
          }
        },
        {
          "languageCode": "ss",
          "languageName": {
            "simpleText": "Swati"
          }
        },
        {
          "languageCode": "sv",
          "languageName": {
            "simpleText": "Swedish"
          }
        },
        {
          "languageCode": "tg",
          "languageName": {
            "simpleText": "Tajik"
          }
        },
        {
          "languageCode": "ta",
          "languageName": {
            "simpleText": "Tamil"
          }
        },
        {
          "languageCode": "tt",
          "languageName": {
            "simpleText": "Tatar"
          }
        },
        {
          "languageCode": "te",
          "languageName": {
            "simpleText": "Telugu"
          }
        },
        {
          "languageCode": "th",
          "languageName": {
            "simpleText": "Thai"
          }
        },
        {
          "languageCode": "bo",
          "languageName": {
            "simpleText": "Tibetan"
          }
        },
        {
          "languageCode": "ti",
          "languageName": {
            "simpleText": "Tigrinya"
          }
        },
        {
          "languageCode": "to",
          "languageName": {
            "simpleText": "Tongan"
          }
        },
        {
          "languageCode": "ts",
          "languageName": {
            "simpleText": "Tsonga"
          }
        },
        {
          "languageCode": "tn",
          "languageName": {
            "simpleText": "Tswana"
          }
        },
        {
          "languageCode": "tum",
          "languageName": {
            "simpleText": "Tumbuka"
          }
        },
        {
          "languageCode": "tr",
          "languageName": {
            "simpleText": "Turkish"
          }
        },
        {
          "languageCode": "tk",
          "languageName": {
            "simpleText": "Turkmen"
          }
        },
        {
          "languageCode": "uk",
          "languageName": {
            "simpleText": "Ukrainian"
          }
        },
        {
          "languageCode": "ur",
          "languageName": {
            "simpleText": "Urdu"
          }
        },
        {
          "languageCode": "ug",
          "languageName": {
            "simpleText": "Uyghur"
          }
        },
        {
          "languageCode": "uz",
          "languageName": {
            "simpleText": "Uzbek"
          }
        },
        {
          "languageCode": "ve",
          "languageName": {
            "simpleText": "Venda"
          }
        },
        {
          "languageCode": "vi",
          "languageName": {
            "simpleText": "Vietnamese"
          }
        },
        {
          "languageCode": "war",
          "languageName": {
            "simpleText": "Waray"
          }
        },
        {
          "languageCode": "cy",
          "languageName": {
            "simpleText": "Welsh"
          }
        },
        {
          "languageCode": "fy",
          "languageName": {
            "simpleText": "Western Frisian"
          }
        },
        {
          "languageCode": "wo",
          "languageName": {
            "simpleText": "Wolof"
          }
        },
        {
          "languageCode": "xh",
          "languageName": {
            "simpleText": "Xhosa"
          }
        },
        {
          "languageCode": "yi",
          "languageName": {
            "simpleText": "Yiddish"
          }
        },
        {
          "languageCode": "yo",
          "languageName": {
            "simpleText": "Yoruba"
          }
        },
        {
          "languageCode": "zu",
          "languageName": {
            "simpleText": "Zulu"
          }
        }
      ],
      "defaultAudioTrackIndex": 0
    }
  },
  "videoDetails": {
    "videoId": "mbtQAqqoHt0",
    "title": "[full] 당신의 직업은 안녕하십니까? - 신년기획 ＜멋진 신AI세계＞ 1부  | 추적60분 1438회 예고 KBS 방송",
    "lengthSeconds": "2919",
    "keywords": [
      "KBS",
      "다큐",
      "다큐멘터리",
      "인터뷰",
      "레전드",
      "그것이 알고싶다"
    ],
    "channelId": "UCy-6oZwPwrR_W-zYnqLD8dg",
    "isOwnerViewing": false,
    "shortDescription": "[1438회] 신년기획: 멋진 신AI세계 1부 – 당신의 직업은 안녕하십니까? / 2026년 1월 2일 22:00 방송\n\n 상상 속에서나 존재하던 미래 기술들이 어느새 우리 곁에 도착했다. 식당에 들어서면 서빙 로봇이 음식을 배달하고 사무실에 앉아 있으면 생성형 AI가 업무를 보조한다. 인공지능은 인간의 삶을 한 번도 경험해 보지 못한 곳으로 이끌고 있다. \n\n 지금 이 순간에도 발전을 거듭하고 있는 AI. 최근 산업연구원은 AI로 대체될 일자리를 327만 개로 추산했다. 이미 AI는 단순 반복 업무를 대체하는 것을 넘어 판단이 필요한 관리 업무까지 대체해 나가고 있다. AI는 어디로 향하고 있는가. 우리는 어떤 미래로 가고 있는가. 2026년 새해 추적 60분이 던지는 첫 번째 질문은 ‘인간 노동의 미래’다. \n\n AI시대, 당신의 직업은 안녕하십니까.   \n\n■ AI 신입사원, 채용시장의 대격변\n 지난해 12월, 정부 서울청사 앞에서는 매주 월요일마다 집회가 열렸다. 이른바 ‘수습 회계사 미지정 사태’ 해결을 위한 농성이다. 2025년 공인회계사 시험 합격자 가운데 수습 기관에 배정된 인원은 전체의 약 26%에 불과했다. 시험 합격자 중 많은 수가 자격증은 있지만 어디에도 소속되지 못한 ‘미지정 회계사’ 상태인 것이다. 시위대는 경기 침체 등을 고려하지 못한 금융위의 잘못된 수요 예측을 지적했다. \n\n 한때는 안정적인 직업의 대명사였던 회계사. 그만큼 시험 합격의 문도 좁았다. 5년 가까이 공부해 회계사 시험에 합격했다는 박현진(가명) 씨. 합격의 기쁨은 잠시였다. 수십 군데에 지원하고 면접을 봤지만 일자리를 찾지 못했다. 선배들에게서 “1년 차 회계사를 가르치는 것보다 AI를 사용하는 것이 시간과 비용 측면에서 절약된다.”는 이야기를 듣다 보면 더욱 암담해진다. 실제로 현장에서 만난 시니어 회계사들은 “AI를 활용해 이전보다 빠르게 업무를 처리하고 있다”고 말한다. 13년 경력의 황병찬 회계사는 “소수의 인원으로도 업무가 돌아가는 상황에서 예전처럼 많은 회계사를 뽑는 것은 사회 흐름과 맞지 않는다,”고 했다. \n\n 개발자 역시 상황은 크게 다르지 않다. 한때 ‘코딩 붐’이 일었던 대한민국. 이제는 개발자를 꿈꾸는 취업 준비생만 남았다. AI가 많은 업무를 대체한 작업 환경에서 더 이상 주니어 개발자가 많이 필요하지 않다. 취업 경쟁률이 수백 대 일이 넘는 현실에 구직자들은 생존을 고민하고 있다. \n\n 이전에 근무했던 경력을 토대로 포트폴리오를 만들고 있는 김현정 씨. AI의 도입 이후 획기적으로 빨라진 코딩 작업 속도를 체감하며 위기의식이 커졌다. 과연 엄청난 속도와 성능을 자랑하는 AI를 이기고 취업할 수 있을까.  \n\n“소위 컴퓨터 앞에 앉아 일하는 사람들은 다 위기예요.”\n노상범 / 15년 차 IT 헤드헌터\n\n■ 리걸 테크, 내 옆의 변호사가 될까\n 지난 2022년 11월 등장한 생성형 AI 서비스 ‘챗GPT’는 사회 전반에 거대한 변화를 불러왔다. 단순 검색을 넘어 업무 파트너로 자리 잡은 AI는 법률 영역에도 깊숙이 들어왔다. 최근 지인을 상대로 한 재판에서 승소한 김수연(가명) 씨. 수연 씨는 가전제품을 싸게 살 수 있게 해주겠다는 지인의 말을 믿고 송금했다. 하지만 그녀에게 돌아온 건 아무것도 없었다. 사기를 인지한 그녀를 도와준 건 다름 아닌 챗GPT. 900만 원가량의 소액 사기로 변호사까지 선임하기엔 비용이 너무 부담됐다. 챗GPT가 알려주는 대로 증거를 수집하고 소장을 작성한 결과는 승소로 이어졌다. \n\n 이런 이들을 돕기 위해 AI 법률 상담 서비스가 개발되기도 했다. 법무법인과 AI 개발 업체가 손잡고 야심 차게 준비했던 서비스는 채 반년도 되지 않아 중단됐다. 변호사법 위반을 들어 대한변호사협회는 해당 법인에 벌금 1,000만 원의 징계를 내렸다. \n\n 변호사들은 “AI의 발전은 거스를 수 없는 시대적 흐름”이라고 입을 모아 얘기한다. 일반인들도 쉽게 접근할 수 있는 법률 서비스의 첫걸음. 리걸 테크는 현실의 벽을 뛰어넘어 법률 서비스가 필요한 사람들에게 다가갈 수 있을까. \n\n“무엇이 맞다, 틀리다를 지금 단정적으로 말씀드릴 수는 없고\n리걸 테크 업체가 할 수 있는 영역이 어디까지인지\n법으로 명확히 규정한다면 리스크가 없어지겠죠.”\n김기일 / ‘ㄷ’ 법무법인 변호사\n\n■ 창작자를 위협하는 인공지능\n  올해 많은 사람의 SNS 프로필 사진을 차지했던 건 단연 ‘지브리풍’ 이미지다. 생성형 AI의 도움으로 만화 속 주인공이 된 사람들. 그 이면에 우리는 어떤 것들을 놓치고 있었을까. AI가 그림체를 따라 할 수 있다는 건 그만큼의 데이터를 학습했다는 의미다. 저작권자의 동의 없이 학습을 진행했다는 사실에 논란이 일기도 했다. 학습 이후 생성된 이미지에는 어떻게 저작권을 물을 수 있을까. 우리는 아직 명확한 답을 찾지 못했다.  \n\n 창작자 고유의 스타일은 그들이 노력해 온 시간의 결과물이다. 작품을 완성하기까지 그들이 흘려온 땀. 이 가치를 인정하고자 우리는 사회적 합의를 통해 창작자들에게 ‘저작권’을 부여했다. 일러스트레이터 이로 씨는 최근 자신의 그림이 AI 사이트에 학습되어 ‘이로 네온 스타일’로 서비스되고 있다는 것을 알게 됐다. 그림을 ‘AI에 학습시키지 말라’는 의사를 표현한 지 오래지만 이제는 보다 근본적인 대책이 필요하다고 느끼고 있다. \n\n 네이버 웹툰의 계약서 역시 창작자들 사이에서 논란이다. 계약서에 명시된 연구 목적의 학습 조항에 동의하지 않으면 계약할 수 없다. 연구 목적과 활용 방식이 불투명한 상황에서, 언젠가 AI에 대체될 수 있다는 두려움은 창작 영역을 넘어 모든 산업으로 확산하고 있다.\n\n“애초에 양질의 데이터가 존재할 수 있는 건 저작자가 있기 때문이에요.\n양질의 데이터를 만들어 낸 저작자가 있고 \n그 저작물이 (AI에) 입력됨으로써 우리가 좋은 결과물을 얻을 수 있는 거거든요.\n어떻게 하면 더 양질의 저작물을 우리가 계속해서\n받아낼 수 있을 것인가를 AI 기업들이 고민해야 할 거 같아요.”\n범유경 / 변호사\n\n■ 다가올 新세계, AI와의 공생\n 10년 전 인공지능 알파고와 대국했던 바둑 프로기사 이세돌 9단. 인간 대 인공지능으로 세계가 주목했던 세기의 경기. 인간의 승리로 가볍게 끝날 것이라 했던 예견과는 달리 알파고가 4대 1로 승리했다. 인공지능이 인간보다 뛰어날 수 있다는 것을 처음으로 증명한 순간에 사람들은 깊이 좌절했다. \n\n 그로부터 10년 후 AI는 진화를 거듭해 ‘카타고’란 이름으로 바둑기사들의 옆에 남았다. 승률을 계산해 승리할 가능성이 높은 자리를 알려주는 ‘블루 스팟’은 프로들이 익히는 기보가 됐다. 10년 먼저 인공지능과의 전투를 치러낸 바둑계. 현재는 공생의 단계로 접어들었다. \n\n 인공지능이란 피할 수 없는 흐름 속에서 대응하고 있는 건 바둑계뿐만이 아니었다. ‘ㅅ’ 회계법인은 AI를 선제적으로 도입해 회계사들과 디지털 역량을 함께 키운다. 디지털 전형의 회계사들을 모집해 실전에서도 AI 리터러시를 활용할 수 있도록 교육한 결과는 앞으로의 성과에서 빛을 발할 것이라 말한다. AI와의 협업은 이제 선택이 아닌 필수다.\n\n“세상에 없던 일이 생긴 거예요. 그래서 규칙을 지금부터 만들어 가야 해요.\n어떤 게 새로 생긴 문제들인가를 나열하고 이게 문제라는 데 합의하고 \n그 문제를 풀기 위해서 대화에 참가해야 할 주체는 누군가를 합의하고.\n전 세계가 같이 마주쳤으니까 우리가 제대로 한다면 \n세계의 표준을 만드는 일이 될 수도 있습니다.”\n박태웅 / 국가인공지능 전략위원회 공공AX분과장\n\n AI의 등장은 인간 노동의 해방일까, 추방일까. AI의 빠른 확산으로 전환점을 맞은 다양한 산업 현장의 현실을 살펴본다.  「 신년기획: 멋진 신AI세계 1부 – 당신의 직업은 안녕하십니까?」 편은 1월 2일 금요일 밤 22:00 KBS 1TV에서 방영된다. \n\nCopyright ⓒ KBS. All rights reserved. 무단 전재, 재배포 및 이용(AI 학습 포함) 금지\n\nSince 1983, 대한민국 최초의 탐사 프로그램\n상식의 눈으로 진실을 추적한다\n매주 금요일 밤 10시 KBS1 《추적60분》\n\n✔ 제보 : 010-4828-0203 / 추적60분 홈페이지 / betterkbs@gmail.com\n▶홈페이지 : https://program.kbs.co.kr/2tv/culture/chu60\n▶카카오톡 채널: http://pf.kakao.com/_fxgiyxj",
    "isCrawlable": true,
    "thumbnail": {
      "thumbnails": [
        {
          "url": "https://i.ytimg.com/vi/mbtQAqqoHt0/hqdefault.jpg?sqp=-oaymwEiCKgBEF5IWvKriqkDFQgBFQAAAAAYASUAAMhCPQCAokN4AQ==&rs=AOn4CLAuHzCyc4azVl_HHCmYufI_Zp1t2A",
          "width": 168,
          "height": 94
        },
        {
          "url": "https://i.ytimg.com/vi/mbtQAqqoHt0/hqdefault.jpg?sqp=-oaymwEiCMQBEG5IWvKriqkDFQgBFQAAAAAYASUAAMhCPQCAokN4AQ==&rs=AOn4CLDqzAXtI_zrM5YN2xqRzFfKrFG2xg",
          "width": 196,
          "height": 110
        },
        {
          "url": "https://i.ytimg.com/vi/mbtQAqqoHt0/hqdefault.jpg?sqp=-oaymwEjCPYBEIoBSFryq4qpAxUIARUAAAAAGAElAADIQj0AgKJDeAE=&rs=AOn4CLB261C_LwbC8JeGof-5IW2DD5c7rA",
          "width": 246,
          "height": 138
        },
        {
          "url": "https://i.ytimg.com/vi/mbtQAqqoHt0/hqdefault.jpg?sqp=-oaymwEjCNACELwBSFryq4qpAxUIARUAAAAAGAElAADIQj0AgKJDeAE=&rs=AOn4CLAifTqMWl0oLXbiGw8jR-3mp8dgGQ",
          "width": 336,
          "height": 188
        },
        {
          "url": "https://i.ytimg.com/vi/mbtQAqqoHt0/maxresdefault.jpg?v=6957b90c",
          "width": 1920,
          "height": 1080
        }
      ]
    },
    "allowRatings": true,
    "viewCount": "64777",
    "author": "KBS 추적60분",
    "isLowLatencyLiveStream": false,
    "isPrivate": false,
    "isUnpluggedCorpus": false,
    "latencyClass": "MDE_STREAM_OPTIMIZATIONS_RENDERER_LATENCY_NORMAL",
    "isLiveContent": false
  },
  "annotations": [
    {
      "playerAnnotationsExpandedRenderer": {
        "featuredChannel": {
          "startTimeMs": "0",
          "endTimeMs": "2919000",
          "watermark": {
            "thumbnails": [
              {
                "url": "https://i.ytimg.com/an/y-6oZwPwrR_W-zYnqLD8dg/featured_channel.jpg?v=649eddd9",
                "width": 40,
                "height": 40
              }
            ]
          },
          "trackingParams": "CAkQ8zciEwjW37yup-6RAxUScPUFHb5cHNo=",
          "navigationEndpoint": {
            "clickTrackingParams": "CAkQ8zciEwjW37yup-6RAxUScPUFHb5cHNoyAml2ygEEcD2g3g==",
            "commandMetadata": {
              "webCommandMetadata": {
                "url": "/channel/UCy-6oZwPwrR_W-zYnqLD8dg",
                "webPageType": "WEB_PAGE_TYPE_CHANNEL",
                "rootVe": 3611,
                "apiUrl": "/youtubei/v1/browse"
              }
            },
            "browseEndpoint": {
              "browseId": "UCy-6oZwPwrR_W-zYnqLD8dg"
            }
          },
          "channelName": "KBS 추적60분",
          "subscribeButton": {
            "subscribeButtonRenderer": {
              "buttonText": {
                "runs": [
                  {
                    "text": "SUBSCRIBE"
                  }
                ]
              },
              "subscribed": false,
              "enabled": true,
              "type": "FREE",
              "channelId": "UCy-6oZwPwrR_W-zYnqLD8dg",
              "showPreferences": false,
              "subscribedButtonText": {
                "runs": [
                  {
                    "text": "SUBSCRIBED"
                  }
                ]
              },
              "unsubscribedButtonText": {
                "runs": [
                  {
                    "text": "SUBSCRIBE"
                  }
                ]
              },
              "trackingParams": "CAoQmysiEwjW37yup-6RAxUScPUFHb5cHNoyAml2",
              "unsubscribeButtonText": {
                "runs": [
                  {
                    "text": "UNSUBSCRIBE"
                  }
                ]
              },
              "serviceEndpoints": [
                {
                  "clickTrackingParams": "CAoQmysiEwjW37yup-6RAxUScPUFHb5cHNoyAml2ygEEcD2g3g==",
                  "commandMetadata": {
                    "webCommandMetadata": {
                      "sendPost": true,
                      "apiUrl": "/youtubei/v1/subscription/subscribe"
                    }
                  },
                  "subscribeEndpoint": {
                    "channelIds": [
                      "UCy-6oZwPwrR_W-zYnqLD8dg"
                    ],
                    "params": "EgIIBBgA"
                  }
                },
                {
                  "clickTrackingParams": "CAoQmysiEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
                  "commandMetadata": {
                    "webCommandMetadata": {
                      "sendPost": true
                    }
                  },
                  "signalServiceEndpoint": {
                    "signal": "CLIENT_SIGNAL",
                    "actions": [
                      {
                        "clickTrackingParams": "CAoQmysiEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
                        "openPopupAction": {
                          "popup": {
                            "confirmDialogRenderer": {
                              "trackingParams": "CAsQxjgiEwjW37yup-6RAxUScPUFHb5cHNo=",
                              "dialogMessages": [
                                {
                                  "runs": [
                                    {
                                      "text": "Unsubscribe from "
                                    },
                                    {
                                      "text": "KBS 추적60분"
                                    },
                                    {
                                      "text": "?"
                                    }
                                  ]
                                }
                              ],
                              "confirmButton": {
                                "buttonRenderer": {
                                  "style": "STYLE_BLUE_TEXT",
                                  "size": "SIZE_DEFAULT",
                                  "isDisabled": false,
                                  "text": {
                                    "runs": [
                                      {
                                        "text": "Unsubscribe"
                                      }
                                    ]
                                  },
                                  "serviceEndpoint": {
                                    "clickTrackingParams": "CA0Q8FsiEwjW37yup-6RAxUScPUFHb5cHNoyAml2ygEEcD2g3g==",
                                    "commandMetadata": {
                                      "webCommandMetadata": {
                                        "sendPost": true,
                                        "apiUrl": "/youtubei/v1/subscription/unsubscribe"
                                      }
                                    },
                                    "unsubscribeEndpoint": {
                                      "channelIds": [
                                        "UCy-6oZwPwrR_W-zYnqLD8dg"
                                      ],
                                      "params": "CgIIBBgA"
                                    }
                                  },
                                  "accessibility": {
                                    "label": "Unsubscribe"
                                  },
                                  "trackingParams": "CA0Q8FsiEwjW37yup-6RAxUScPUFHb5cHNo="
                                }
                              },
                              "cancelButton": {
                                "buttonRenderer": {
                                  "style": "STYLE_TEXT",
                                  "size": "SIZE_DEFAULT",
                                  "isDisabled": false,
                                  "text": {
                                    "runs": [
                                      {
                                        "text": "Cancel"
                                      }
                                    ]
                                  },
                                  "accessibility": {
                                    "label": "Cancel"
                                  },
                                  "trackingParams": "CAwQ8FsiEwjW37yup-6RAxUScPUFHb5cHNo="
                                }
                              },
                              "primaryIsCancel": false
                            }
                          },
                          "popupType": "DIALOG"
                        }
                      }
                    ]
                  }
                }
              ],
              "subscribeAccessibility": {
                "accessibilityData": {
                  "label": "Subscribe to KBS 추적60분."
                }
              },
              "unsubscribeAccessibility": {
                "accessibilityData": {
                  "label": "Unsubscribe from KBS 추적60분."
                }
              },
              "signInEndpoint": {
                "clickTrackingParams": "CAoQmysiEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
                "commandMetadata": {
                  "webCommandMetadata": {
                    "url": "https://accounts.google.com/ServiceLogin?service=youtube&uilel=3&passive=true&continue=http%3A%2F%2Fwww.youtube.com%2Fsignin%3Faction_handle_signin%3Dtrue%26app%3Ddesktop%26hl%3Den%26next%3Dhttps%253A%252F%252Fwww.youtube.com%252Fchannel%252FUCy-6oZwPwrR_W-zYnqLD8dg%26feature%3Div%26continue_action%3DQUFFLUhqbkZ2OUJVU3FHaERERklrajlteFJMbGtBZU5tQXxBQ3Jtc0tsaDNDTlJsUWI5dW9FNWgwaVVXQmhOU0JRd1hxUFlubVBNU3NOQ01KUUlFdDVYdEhoaXMydEZicWpNUUktV29oUkhwLWRUdGFTZE5oZ1prUDJzMS16WlhRM29aTG02WXZQQ0d1RVJNMDNUNmNGX1ZKV19ma0lJVFd1T3JSY21MZEVxWGRrWE5ObU5DUVFYbTdMaGdVTDYzOHNDLXpjYjlfSkY5UTRReDFqbDBpM1NQeTBnelotVVpWX21BVHVQN3o1SjBtazk%253D&hl=en"
                  }
                }
              }
            }
          }
        },
        "allowSwipeDismiss": true,
        "annotationId": "5ed0da5d-0000-24d6-b64e-f403043934dc"
      }
    }
  ],
  "playerConfig": {
    "audioConfig": {
      "loudnessDb": -3.0599995,
      "perceptualLoudnessDb": -17.06,
      "enablePerFormatLoudness": true,
      "trackAbsoluteLoudnessLkfs": -17.06,
      "loudnessTargetLkfs": -14
    },
    "streamSelectionConfig": {
      "maxBitrate": "34400000"
    },
    "mediaCommonConfig": {
      "dynamicReadaheadConfig": {
        "maxReadAheadMediaTimeMs": 120000,
        "minReadAheadMediaTimeMs": 15000,
        "readAheadGrowthRateMs": 1000
      },
      "mediaUstreamerRequestConfig": {
        "videoPlaybackUstreamerConfig": "CvIJCosFCAAlAACAPy0zM3M_NT0Klz9YAWgBchoKFm1mczJfY21mc193ZWJfdjNfMl8wMDMYAKABAagBALgCANoChgEQsOoBGIDd2wEgoJwBKKCcATCYdXCIJ4AB9APgAQOYAgzQAgLoAgSAAwKIA4gnqAMDwAMByAMBgAQB0AQB2AQB-AQHgAV9wAUByAUB4AXQD-gFAfgF0A-QBgHQBgHwBgGAB9APwAcBgAgBiAgBnQjNzEw-oAjoB-AIAegI____________AfoCigEtAACgQjUAAKpCZQAAgEBowHCoAdCGA4UCmpkZP40CAACAP5UC-u1rO7UCAACAP8AC3wP9As3MzD2QAwGdAwrXIz3VAwAAekTVBAAAIEGgBgG1Br03hjW9BjMzg0DABwHIBwHlBwCACUTwBwGACAGhCAAAAAAAAPC_qQgAAAAAAADwv7AI3wO4CgGoAwGwAwPQAwHYAwHKBBwKEwjAqQcQmHUY6AclAAAAACgAMAAQ4NQDGNAP0gQPCggIsAkQsAkgASCIJygB2gQNCgYI8C4Q8C4g8C4oAfAFAZgGAagGgIAC0gYUCOgHEGQaDQiIJxUAAAA_Hc3MTD_YBgHwBgG4BwGgCAHSCAYIARABGAGpCQAAAAAAAPC_sQkAAAAAAADwv9AJAdoJJEtiSnc0dml3TU1hTmxsNXZhUWRjMTlDRUFxbWtVc1JaY2lNReoLBIsGjAaADAGoDJAB4A0ByA8B0A8B6BABkBEBoBEBshEYQ0FNU0RSVU11YmJKRElZT2dnSWd6QVU90BIB4BIBgBMBsBMBkRQAAAAAAADwv5kUAAAAAAAA8L-wFAHKFADYFADoFAGBFQAAAAAAAPC_iKehygsBMgwIiQEQ7fCg86vtkQMyDAj4ARDA7eS0yu2RAzIMCI8DELqd5fOx7ZEDMgwIiAEQjuy5-KrtkQMyDAj3ARCzlM-Kxu2RAzIMCI4DEIjMxaKn7ZEDMgwIhwEQ8OKtkbPtkQMyDAj0ARD4m4Lr0-2RAzIMCI0DENX1wM6m7ZEDMgwIhgEQ8pa9krLtkQMyDAjzARCF87yyv-2RAzIMCIwDEPHrks6k7ZEDMgwIhQEQ-Z-AqrrtkQMyDAjyARCv8ZrF2O2RAzIMCIsDELefvKKg7ZEDMgwIoAEQ3sfv2r3tkQMyDAiWAhCgtLTFwu2RAzIMCIoDEJLRgdag7ZEDMgwIjAEQ9qff5ZrtkQMyHAiMARCh2-eUpO2RAxoOQ2dnS0EyUnlZeElCTVEyGgiMARDUmZqs8eyRAxoMQ2djS0FuWmlFZ0V4MgwI-QEQspHW0p_tkQMyHAj5ARD2qLahpO2RAxoOQ2dnS0EyUnlZeElCTVEyGgj5ARD-hJPL8eyRAxoMQ2djS0FuWmlFZ0V4MgwI-gEQ2d7E6p_tkQMyHAj6ARDs0fOjpO2RAxoOQ2dnS0EyUnlZeElCTVEyGgj6ARCLg7fL8eyRAxoMQ2djS0FuWmlFZ0V4MgwI-wEQo-WrgKDtkQMyHAj7ARDjr7abpO2RAxoOQ2dnS0EyUnlZeElCTVEyGgj7ARDLzZ7L8eyRAxoMQ2djS0FuWmlFZ0V4OgBSKhoCa28oADIYVUN5LTZvWndQd3JSX1ctellucUxEOGRnOABAAFgAYAB4AKABAbABBboBAwQFMcIBCAECAwQFCDBe0AEAEksA-VxNBjBEAiBDfJL9hW-lFSeczOKwOSNqgzYI0sGjD-oKI7FQY-VzkwIgFTZmJZx1MrHLhO3jFlXZuGbFGqnPsiXBehWdKJuVb5UaAmVp"
      },
      "useServerDrivenAbr": true,
      "serverPlaybackStartConfig": {
        "enable": true,
        "playbackStartPolicy": {
          "startMinReadaheadPolicy": [
            {
              "minReadaheadMs": 1200
            }
          ]
        }
      },
      "platypusUseEnvoyNetFetch": false,
      "fixLivePlaybackModelDefaultPosition": false
    },
    "webPlayerConfig": {
      "useCobaltTvosDash": true,
      "webPlayerActionsPorting": {
        "getSharePanelCommand": {
          "clickTrackingParams": "CAAQu2kiEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
          "commandMetadata": {
            "webCommandMetadata": {
              "sendPost": true,
              "apiUrl": "/youtubei/v1/share/get_web_player_share_panel"
            }
          },
          "webPlayerShareEntityServiceEndpoint": {
            "serializedShareEntity": "CgttYnRRQXFxb0h0MA%3D%3D"
          }
        },
        "subscribeCommand": {
          "clickTrackingParams": "CAAQu2kiEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
          "commandMetadata": {
            "webCommandMetadata": {
              "sendPost": true,
              "apiUrl": "/youtubei/v1/subscription/subscribe"
            }
          },
          "subscribeEndpoint": {
            "channelIds": [
              "UCy-6oZwPwrR_W-zYnqLD8dg"
            ],
            "params": "EgIIBxgA"
          }
        },
        "unsubscribeCommand": {
          "clickTrackingParams": "CAAQu2kiEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
          "commandMetadata": {
            "webCommandMetadata": {
              "sendPost": true,
              "apiUrl": "/youtubei/v1/subscription/unsubscribe"
            }
          },
          "unsubscribeEndpoint": {
            "channelIds": [
              "UCy-6oZwPwrR_W-zYnqLD8dg"
            ],
            "params": "CgIIBxgA"
          }
        },
        "addToWatchLaterCommand": {
          "clickTrackingParams": "CAAQu2kiEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
          "commandMetadata": {
            "webCommandMetadata": {
              "sendPost": true,
              "apiUrl": "/youtubei/v1/browse/edit_playlist"
            }
          },
          "playlistEditEndpoint": {
            "playlistId": "WL",
            "actions": [
              {
                "addedVideoId": "mbtQAqqoHt0",
                "action": "ACTION_ADD_VIDEO"
              }
            ]
          }
        },
        "removeFromWatchLaterCommand": {
          "clickTrackingParams": "CAAQu2kiEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
          "commandMetadata": {
            "webCommandMetadata": {
              "sendPost": true,
              "apiUrl": "/youtubei/v1/browse/edit_playlist"
            }
          },
          "playlistEditEndpoint": {
            "playlistId": "WL",
            "actions": [
              {
                "action": "ACTION_REMOVE_VIDEO_BY_VIDEO_ID",
                "removedVideoId": "mbtQAqqoHt0"
              }
            ]
          }
        }
      }
    }
  },
  "storyboards": {
    "playerStoryboardSpecRenderer": {
      "spec": "https://i.ytimg.com/sb/mbtQAqqoHt0/storyboard3_L$L/$N.jpg?sqp=-oaymwGhAUg48quKqQOYAYgBAZUBAAAEQpgBMqABPKgBBLIBQBANDBAVHyYtDg4PEhcrLCkPDhAVHyoyKQ8RFBgmPTgtERQeKjFLRzYVHCkuOUdNPyUuNz1HUlFFM0BCQ0xERkO6AUARERUjRENDQxETFi9DQ0NDFRYpQ0NDQ0MjL0NDQ0NDQ0RDQ0NDQ0JCQ0NDQ0NCQkJDQ0NDQkJCQkNDQ0JCQkJCovOX_wMGCI7x3soG|48#27#100#10#10#0#default#rs$AOn4CLCehY4fPWFgYpye2zXNkky9EhGlBA|80#45#293#10#10#10000#M$M#rs$AOn4CLDfaKyHN21-vuAZJ2WywkDupYu16Q|160#90#293#5#5#10000#M$M#rs$AOn4CLBTSDZFqMzXUA7M4sB9AskX6xR4ww|320#180#293#3#3#10000#M$M#rs$AOn4CLD8SjZpToo0OedcVml7TBoUPVXQGw",
      "recommendedLevel": 3,
      "fineScrubbingRecommendedLevel": 2,
      "highResolutionRecommendedLevel": 3
    }
  },
  "microformat": {
    "playerMicroformatRenderer": {
      "thumbnail": {
        "thumbnails": [
          {
            "url": "https://i.ytimg.com/vi/mbtQAqqoHt0/maxresdefault.jpg",
            "width": 1280,
            "height": 720
          }
        ]
      },
      "embed": {
        "iframeUrl": "https://www.youtube.com/embed/mbtQAqqoHt0",
        "width": 1280,
        "height": 720
      },
      "title": {
        "simpleText": "[full] 당신의 직업은 안녕하십니까? - 신년기획 ＜멋진 신AI세계＞ 1부  | 추적60분 1438회 예고 KBS 방송"
      },
      "description": {
        "simpleText": "[1438회] 신년기획: 멋진 신AI세계 1부 – 당신의 직업은 안녕하십니까? / 2026년 1월 2일 22:00 방송\n\n 상상 속에서나 존재하던 미래 기술들이 어느새 우리 곁에 도착했다. 식당에 들어서면 서빙 로봇이 음식을 배달하고 사무실에 앉아 있으면 생성형 AI가 업무를 보조한다. 인공지능은 인간의 삶을 한 번도 경험해 보지 못한 곳으로 이끌고 있다. \n\n 지금 이 순간에도 발전을 거듭하고 있는 AI. 최근 산업연구원은 AI로 대체될 일자리를 327만 개로 추산했다. 이미 AI는 단순 반복 업무를 대체하는 것을 넘어 판단이 필요한 관리 업무까지 대체해 나가고 있다. AI는 어디로 향하고 있는가. 우리는 어떤 미래로 가고 있는가. 2026년 새해 추적 60분이 던지는 첫 번째 질문은 ‘인간 노동의 미래’다. \n\n AI시대, 당신의 직업은 안녕하십니까.   \n\n■ AI 신입사원, 채용시장의 대격변\n 지난해 12월, 정부 서울청사 앞에서는 매주 월요일마다 집회가 열렸다. 이른바 ‘수습 회계사 미지정 사태’ 해결을 위한 농성이다. 2025년 공인회계사 시험 합격자 가운데 수습 기관에 배정된 인원은 전체의 약 26%에 불과했다. 시험 합격자 중 많은 수가 자격증은 있지만 어디에도 소속되지 못한 ‘미지정 회계사’ 상태인 것이다. 시위대는 경기 침체 등을 고려하지 못한 금융위의 잘못된 수요 예측을 지적했다. \n\n 한때는 안정적인 직업의 대명사였던 회계사. 그만큼 시험 합격의 문도 좁았다. 5년 가까이 공부해 회계사 시험에 합격했다는 박현진(가명) 씨. 합격의 기쁨은 잠시였다. 수십 군데에 지원하고 면접을 봤지만 일자리를 찾지 못했다. 선배들에게서 “1년 차 회계사를 가르치는 것보다 AI를 사용하는 것이 시간과 비용 측면에서 절약된다.”는 이야기를 듣다 보면 더욱 암담해진다. 실제로 현장에서 만난 시니어 회계사들은 “AI를 활용해 이전보다 빠르게 업무를 처리하고 있다”고 말한다. 13년 경력의 황병찬 회계사는 “소수의 인원으로도 업무가 돌아가는 상황에서 예전처럼 많은 회계사를 뽑는 것은 사회 흐름과 맞지 않는다,”고 했다. \n\n 개발자 역시 상황은 크게 다르지 않다. 한때 ‘코딩 붐’이 일었던 대한민국. 이제는 개발자를 꿈꾸는 취업 준비생만 남았다. AI가 많은 업무를 대체한 작업 환경에서 더 이상 주니어 개발자가 많이 필요하지 않다. 취업 경쟁률이 수백 대 일이 넘는 현실에 구직자들은 생존을 고민하고 있다. \n\n 이전에 근무했던 경력을 토대로 포트폴리오를 만들고 있는 김현정 씨. AI의 도입 이후 획기적으로 빨라진 코딩 작업 속도를 체감하며 위기의식이 커졌다. 과연 엄청난 속도와 성능을 자랑하는 AI를 이기고 취업할 수 있을까.  \n\n“소위 컴퓨터 앞에 앉아 일하는 사람들은 다 위기예요.”\n노상범 / 15년 차 IT 헤드헌터\n\n■ 리걸 테크, 내 옆의 변호사가 될까\n 지난 2022년 11월 등장한 생성형 AI 서비스 ‘챗GPT’는 사회 전반에 거대한 변화를 불러왔다. 단순 검색을 넘어 업무 파트너로 자리 잡은 AI는 법률 영역에도 깊숙이 들어왔다. 최근 지인을 상대로 한 재판에서 승소한 김수연(가명) 씨. 수연 씨는 가전제품을 싸게 살 수 있게 해주겠다는 지인의 말을 믿고 송금했다. 하지만 그녀에게 돌아온 건 아무것도 없었다. 사기를 인지한 그녀를 도와준 건 다름 아닌 챗GPT. 900만 원가량의 소액 사기로 변호사까지 선임하기엔 비용이 너무 부담됐다. 챗GPT가 알려주는 대로 증거를 수집하고 소장을 작성한 결과는 승소로 이어졌다. \n\n 이런 이들을 돕기 위해 AI 법률 상담 서비스가 개발되기도 했다. 법무법인과 AI 개발 업체가 손잡고 야심 차게 준비했던 서비스는 채 반년도 되지 않아 중단됐다. 변호사법 위반을 들어 대한변호사협회는 해당 법인에 벌금 1,000만 원의 징계를 내렸다. \n\n 변호사들은 “AI의 발전은 거스를 수 없는 시대적 흐름”이라고 입을 모아 얘기한다. 일반인들도 쉽게 접근할 수 있는 법률 서비스의 첫걸음. 리걸 테크는 현실의 벽을 뛰어넘어 법률 서비스가 필요한 사람들에게 다가갈 수 있을까. \n\n“무엇이 맞다, 틀리다를 지금 단정적으로 말씀드릴 수는 없고\n리걸 테크 업체가 할 수 있는 영역이 어디까지인지\n법으로 명확히 규정한다면 리스크가 없어지겠죠.”\n김기일 / ‘ㄷ’ 법무법인 변호사\n\n■ 창작자를 위협하는 인공지능\n  올해 많은 사람의 SNS 프로필 사진을 차지했던 건 단연 ‘지브리풍’ 이미지다. 생성형 AI의 도움으로 만화 속 주인공이 된 사람들. 그 이면에 우리는 어떤 것들을 놓치고 있었을까. AI가 그림체를 따라 할 수 있다는 건 그만큼의 데이터를 학습했다는 의미다. 저작권자의 동의 없이 학습을 진행했다는 사실에 논란이 일기도 했다. 학습 이후 생성된 이미지에는 어떻게 저작권을 물을 수 있을까. 우리는 아직 명확한 답을 찾지 못했다.  \n\n 창작자 고유의 스타일은 그들이 노력해 온 시간의 결과물이다. 작품을 완성하기까지 그들이 흘려온 땀. 이 가치를 인정하고자 우리는 사회적 합의를 통해 창작자들에게 ‘저작권’을 부여했다. 일러스트레이터 이로 씨는 최근 자신의 그림이 AI 사이트에 학습되어 ‘이로 네온 스타일’로 서비스되고 있다는 것을 알게 됐다. 그림을 ‘AI에 학습시키지 말라’는 의사를 표현한 지 오래지만 이제는 보다 근본적인 대책이 필요하다고 느끼고 있다. \n\n 네이버 웹툰의 계약서 역시 창작자들 사이에서 논란이다. 계약서에 명시된 연구 목적의 학습 조항에 동의하지 않으면 계약할 수 없다. 연구 목적과 활용 방식이 불투명한 상황에서, 언젠가 AI에 대체될 수 있다는 두려움은 창작 영역을 넘어 모든 산업으로 확산하고 있다.\n\n“애초에 양질의 데이터가 존재할 수 있는 건 저작자가 있기 때문이에요.\n양질의 데이터를 만들어 낸 저작자가 있고 \n그 저작물이 (AI에) 입력됨으로써 우리가 좋은 결과물을 얻을 수 있는 거거든요.\n어떻게 하면 더 양질의 저작물을 우리가 계속해서\n받아낼 수 있을 것인가를 AI 기업들이 고민해야 할 거 같아요.”\n범유경 / 변호사\n\n■ 다가올 新세계, AI와의 공생\n 10년 전 인공지능 알파고와 대국했던 바둑 프로기사 이세돌 9단. 인간 대 인공지능으로 세계가 주목했던 세기의 경기. 인간의 승리로 가볍게 끝날 것이라 했던 예견과는 달리 알파고가 4대 1로 승리했다. 인공지능이 인간보다 뛰어날 수 있다는 것을 처음으로 증명한 순간에 사람들은 깊이 좌절했다. \n\n 그로부터 10년 후 AI는 진화를 거듭해 ‘카타고’란 이름으로 바둑기사들의 옆에 남았다. 승률을 계산해 승리할 가능성이 높은 자리를 알려주는 ‘블루 스팟’은 프로들이 익히는 기보가 됐다. 10년 먼저 인공지능과의 전투를 치러낸 바둑계. 현재는 공생의 단계로 접어들었다. \n\n 인공지능이란 피할 수 없는 흐름 속에서 대응하고 있는 건 바둑계뿐만이 아니었다. ‘ㅅ’ 회계법인은 AI를 선제적으로 도입해 회계사들과 디지털 역량을 함께 키운다. 디지털 전형의 회계사들을 모집해 실전에서도 AI 리터러시를 활용할 수 있도록 교육한 결과는 앞으로의 성과에서 빛을 발할 것이라 말한다. AI와의 협업은 이제 선택이 아닌 필수다.\n\n“세상에 없던 일이 생긴 거예요. 그래서 규칙을 지금부터 만들어 가야 해요.\n어떤 게 새로 생긴 문제들인가를 나열하고 이게 문제라는 데 합의하고 \n그 문제를 풀기 위해서 대화에 참가해야 할 주체는 누군가를 합의하고.\n전 세계가 같이 마주쳤으니까 우리가 제대로 한다면 \n세계의 표준을 만드는 일이 될 수도 있습니다.”\n박태웅 / 국가인공지능 전략위원회 공공AX분과장\n\n AI의 등장은 인간 노동의 해방일까, 추방일까. AI의 빠른 확산으로 전환점을 맞은 다양한 산업 현장의 현실을 살펴본다.  「 신년기획: 멋진 신AI세계 1부 – 당신의 직업은 안녕하십니까?」 편은 1월 2일 금요일 밤 22:00 KBS 1TV에서 방영된다. \n\nCopyright ⓒ KBS. All rights reserved. 무단 전재, 재배포 및 이용(AI 학습 포함) 금지\n\nSince 1983, 대한민국 최초의 탐사 프로그램\n상식의 눈으로 진실을 추적한다\n매주 금요일 밤 10시 KBS1 《추적60분》\n\n✔ 제보 : 010-4828-0203 / 추적60분 홈페이지 / betterkbs@gmail.com\n▶홈페이지 : https://program.kbs.co.kr/2tv/culture/chu60\n▶카카오톡 채널: http://pf.kakao.com/_fxgiyxj"
      },
      "lengthSeconds": "2919",
      "ownerProfileUrl": "http://www.youtube.com/@KBS60min",
      "externalChannelId": "UCy-6oZwPwrR_W-zYnqLD8dg",
      "isFamilySafe": true,
      "availableCountries": [
        "AD",
        "AE",
        "AF",
        "AG",
        "AI",
        "AL",
        "AM",
        "AO",
        "AQ",
        "AR",
        "AS",
        "AT",
        "AU",
        "AW",
        "AX",
        "AZ",
        "BA",
        "BB",
        "BD",
        "BE",
        "BF",
        "BG",
        "BH",
        "BI",
        "BJ",
        "BL",
        "BM",
        "BN",
        "BO",
        "BQ",
        "BR",
        "BS",
        "BT",
        "BV",
        "BW",
        "BY",
        "BZ",
        "CA",
        "CC",
        "CD",
        "CF",
        "CG",
        "CH",
        "CI",
        "CK",
        "CL",
        "CM",
        "CN",
        "CO",
        "CR",
        "CU",
        "CV",
        "CW",
        "CX",
        "CY",
        "CZ",
        "DE",
        "DJ",
        "DK",
        "DM",
        "DO",
        "DZ",
        "EC",
        "EE",
        "EG",
        "EH",
        "ER",
        "ES",
        "ET",
        "FI",
        "FJ",
        "FK",
        "FM",
        "FO",
        "FR",
        "GA",
        "GB",
        "GD",
        "GE",
        "GF",
        "GG",
        "GH",
        "GI",
        "GL",
        "GM",
        "GN",
        "GP",
        "GQ",
        "GR",
        "GS",
        "GT",
        "GU",
        "GW",
        "GY",
        "HK",
        "HM",
        "HN",
        "HR",
        "HT",
        "HU",
        "ID",
        "IE",
        "IL",
        "IM",
        "IN",
        "IO",
        "IQ",
        "IR",
        "IS",
        "IT",
        "JE",
        "JM",
        "JO",
        "JP",
        "KE",
        "KG",
        "KH",
        "KI",
        "KM",
        "KN",
        "KP",
        "KR",
        "KW",
        "KY",
        "KZ",
        "LA",
        "LB",
        "LC",
        "LI",
        "LK",
        "LR",
        "LS",
        "LT",
        "LU",
        "LV",
        "LY",
        "MA",
        "MC",
        "MD",
        "ME",
        "MF",
        "MG",
        "MH",
        "MK",
        "ML",
        "MM",
        "MN",
        "MO",
        "MP",
        "MQ",
        "MR",
        "MS",
        "MT",
        "MU",
        "MV",
        "MW",
        "MX",
        "MY",
        "MZ",
        "NA",
        "NC",
        "NE",
        "NF",
        "NG",
        "NI",
        "NL",
        "NO",
        "NP",
        "NR",
        "NU",
        "NZ",
        "OM",
        "PA",
        "PE",
        "PF",
        "PG",
        "PH",
        "PK",
        "PL",
        "PM",
        "PN",
        "PR",
        "PS",
        "PT",
        "PW",
        "PY",
        "QA",
        "RE",
        "RO",
        "RS",
        "RU",
        "RW",
        "SA",
        "SB",
        "SC",
        "SD",
        "SE",
        "SG",
        "SH",
        "SI",
        "SJ",
        "SK",
        "SL",
        "SM",
        "SN",
        "SO",
        "SR",
        "SS",
        "ST",
        "SV",
        "SX",
        "SY",
        "SZ",
        "TC",
        "TD",
        "TF",
        "TG",
        "TH",
        "TJ",
        "TK",
        "TL",
        "TM",
        "TN",
        "TO",
        "TR",
        "TT",
        "TV",
        "TW",
        "TZ",
        "UA",
        "UG",
        "UM",
        "US",
        "UY",
        "UZ",
        "VA",
        "VC",
        "VE",
        "VG",
        "VI",
        "VN",
        "VU",
        "WF",
        "WS",
        "YE",
        "YT",
        "ZA",
        "ZM",
        "ZW"
      ],
      "isUnlisted": false,
      "hasYpcMetadata": false,
      "viewCount": "64777",
      "category": "News & Politics",
      "publishDate": "2026-01-02T05:00:06-08:00",
      "ownerChannelName": "KBS 추적60분",
      "liveBroadcastDetails": {
        "isLiveNow": false,
        "startTimestamp": "2026-01-02T13:00:06+00:00",
        "endTimestamp": "2026-01-02T13:49:45+00:00"
      },
      "uploadDate": "2026-01-02T05:00:06-08:00",
      "isShortsEligible": false,
      "externalVideoId": "mbtQAqqoHt0",
      "likeCount": "1425",
      "canonicalUrl": "https://www.youtube.com/watch?v=mbtQAqqoHt0"
    }
  },
  "cards": {
    "cardCollectionRenderer": {
      "cards": [
        {
          "cardRenderer": {
            "teaser": {
              "simpleCardTeaserRenderer": {
                "message": {
                  "simpleText": "View corrections"
                },
                "trackingParams": "CAgQ0DYiEwjW37yup-6RAxUScPUFHb5cHNo=",
                "prominent": true,
                "logVisibilityUpdates": true,
                "onTapCommand": {
                  "clickTrackingParams": "CAgQ0DYiEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
                  "changeEngagementPanelVisibilityAction": {
                    "targetId": "engagement-panel-error-corrections",
                    "visibility": "ENGAGEMENT_PANEL_VISIBILITY_EXPANDED"
                  }
                }
              }
            },
            "cueRanges": [
              {
                "startCardActiveMs": "0",
                "endCardActiveMs": "5000",
                "teaserDurationMs": "6000",
                "iconAfterTeaserMs": "5000"
              }
            ],
            "trackingParams": "CAcQtZcBGAAiEwjW37yup-6RAxUScPUFHb5cHNo="
          }
        }
      ],
      "headerText": {
        "simpleText": "From KBS 추적60분"
      },
      "icon": {
        "infoCardIconRenderer": {
          "trackingParams": "CAYQsJcBIhMI1t-8rqfukQMVEnD1BR2-XBza"
        }
      },
      "closeButton": {
        "infoCardIconRenderer": {
          "trackingParams": "CAUQsZcBIhMI1t-8rqfukQMVEnD1BR2-XBza"
        }
      },
      "trackingParams": "CAQQwjciEwjW37yup-6RAxUScPUFHb5cHNo=",
      "allowTeaserDismiss": true,
      "logIconVisibilityUpdates": true
    }
  },
  "trackingParams": "CAAQu2kiEwjW37yup-6RAxUScPUFHb5cHNo=",
  "messages": [
    {
      "mealbarPromoRenderer": {
        "icon": {
          "thumbnails": [
            {
              "url": "https://www.gstatic.com/youtube/img/promos/growth/6ad5a99c727579634bc3e2fb67562a2621170bdd11578967392667be5a05c5e4_384x384.png",
              "width": 384,
              "height": 384
            }
          ]
        },
        "messageTexts": [
          {
            "runs": [
              {
                "text": "Ad-free YouTube and access to YouTube Music"
              }
            ]
          }
        ],
        "actionButton": {
          "buttonRenderer": {
            "style": "STYLE_MONO_FILLED",
            "size": "SIZE_DEFAULT",
            "text": {
              "runs": [
                {
                  "text": "1 month free"
                }
              ]
            },
            "trackingParams": "CAMQ7G8iEwjW37yup-6RAxUScPUFHb5cHNo=",
            "command": {
              "clickTrackingParams": "CAMQ7G8iEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
              "commandExecutorCommand": {
                "commands": [
                  {
                    "clickTrackingParams": "CAMQ7G8iEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
                    "commandMetadata": {
                      "webCommandMetadata": {
                        "url": "/premium?ybp=Eg9GRXdoYXRfdG9fd2F0Y2gqEmRtZWEtYWNxLWMtZWdzb0tSZToaCAYYASoUChJkbWVhLWFjcS1jLWVnc29LUmU%253D",
                        "webPageType": "WEB_PAGE_TYPE_BROWSE",
                        "rootVe": 93498,
                        "apiUrl": "/youtubei/v1/browse"
                      }
                    },
                    "browseEndpoint": {
                      "browseId": "SPunlimited",
                      "params": "kgNBEg9GRXdoYXRfdG9fd2F0Y2gqEmRtZWEtYWNxLWMtZWdzb0tSZToaCAYYASoUChJkbWVhLWFjcS1jLWVnc29LUmU%3D"
                    }
                  },
                  {
                    "commandMetadata": {
                      "webCommandMetadata": {
                        "sendPost": true,
                        "apiUrl": "/youtubei/v1/feedback"
                      }
                    },
                    "feedbackEndpoint": {
                      "feedbackToken": "AB9zfpJPIF6M743DDvm109X-ned23Q49mtYjmMKggE3MWemgMqvciU2YBpFQXUXEKwgZngvpFXcVGTn13HTB5EjC0bS1aYDRvQZqi7iBs7hVrS8UfS-0n-TJpaso9rDU3NHwC0bhWEA2lGRTOlrAGTurR4ktZYidmotsKg7yAVnzaSwY94ZGr90",
                      "uiActions": {
                        "hideEnclosingContainer": true
                      }
                    }
                  }
                ]
              }
            }
          }
        },
        "dismissButton": {
          "buttonRenderer": {
            "style": "STYLE_MONO_TONAL",
            "size": "SIZE_DEFAULT",
            "text": {
              "runs": [
                {
                  "text": "No thanks"
                }
              ]
            },
            "trackingParams": "CAIQ7W8iEwjW37yup-6RAxUScPUFHb5cHNo=",
            "command": {
              "clickTrackingParams": "CAIQ7W8iEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
              "commandExecutorCommand": {
                "commands": [
                  {
                    "clickTrackingParams": "CAIQ7W8iEwjW37yup-6RAxUScPUFHb5cHNrKAQRwPaDe",
                    "commandMetadata": {
                      "webCommandMetadata": {
                        "sendPost": true,
                        "apiUrl": "/youtubei/v1/feedback"
                      }
                    },
                    "feedbackEndpoint": {
                      "feedbackToken": "AB9zfpLBzIUtuaYXzXYt9p4bylxl0ENO-pvK11BK16a-ZpbcqRvWPJ-AuBw2amRP_gBbP6vKmz7qWf629TaT9rV3n_VXtsub0SPIhMaE4DTVRCfkIQVFiqB_Afg2fXIgiy187d-FKcU1eNBJLiAzpDD_Ns3NMbLogBGlistm3wwKbepuuKUNh00",
                      "uiActions": {
                        "hideEnclosingContainer": true
                      }
                    }
                  }
                ]
              }
            }
          }
        },
        "triggerCondition": "TRIGGER_CONDITION_POST_AD",
        "style": "STYLE_MODERN",
        "trackingParams": "CAEQ42kYASITCNbfvK6n7pEDFRJw9QUdvlwc2g==",
        "impressionEndpoints": [
          {
            "clickTrackingParams": "CAEQ42kYASITCNbfvK6n7pEDFRJw9QUdvlwc2soBBHA9oN4=",
            "commandMetadata": {
              "webCommandMetadata": {
                "sendPost": true,
                "apiUrl": "/youtubei/v1/feedback"
              }
            },
            "feedbackEndpoint": {
              "feedbackToken": "AB9zfpLbv3u6PPUKrOOQI3ik6fMmEM46NYzIFfscYse5ujfgSOHUGEMnMofzsNaz1BTuh0lOlCBuKWH7PxDhjCxW-WiaCHhgGlJy8gvoGnRxGjcIjIZ6Pu7KQYtjf0UV0q85KN7uQKAXBGYoDUq-8G5X7n3l5avbW0JCihXVaJcf5tpIeTI8GaI",
              "uiActions": {
                "hideEnclosingContainer": false
              }
            }
          }
        ],
        "isVisible": true,
        "messageTitle": {
          "runs": [
            {
              "text": "YouTube Premium"
            }
          ]
        },
        "iconDark": {
          "thumbnails": [
            {
              "url": "https://www.gstatic.com/youtube/img/promos/growth/6ad5a99c727579634bc3e2fb67562a2621170bdd11578967392667be5a05c5e4_384x384.png",
              "width": 384,
              "height": 384
            }
          ]
        },
        "supplementalText": {
          "runs": [
            {
              "text": "Terms apply. Cancel anytime"
            }
          ]
        }
      }
    }
  ],
  "adBreakHeartbeatParams": "Q0FBJTNE",
  "frameworkUpdates": {
    "entityBatchUpdate": {
      "mutations": [
        {
          "entityKey": "Eg0KC21idFFBcXFvSHQwIPYBKAE%3D",
          "type": "ENTITY_MUTATION_TYPE_REPLACE",
          "payload": {
            "offlineabilityEntity": {
              "key": "Eg0KC21idFFBcXFvSHQwIPYBKAE%3D",
              "addToOfflineButtonState": "ADD_TO_OFFLINE_BUTTON_STATE_UNKNOWN"
            }
          }
        }
      ],
      "timestamp": {
        "seconds": "1767406788",
        "nanos": 667667880
      }
    }
  }
}
```