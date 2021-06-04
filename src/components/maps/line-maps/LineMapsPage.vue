<template>
  <div class="line-maps-page">
    <div class="row">
      <div class="flex md12 xs12">
        <va-card
          class="line-maps-page__widget"
          title="Line Maps"
        >
          <!--          <line-map-->
          <!--            :map-data="lineMapData"-->
          <!--            style="height: 65vh;"-->
          <!--          />-->
          <va-card
            :image='images[5]'
            square
            titleOnImage
          >

          </va-card>
        </va-card>
      </div>
    </div>
  </div>
</template>

<script>
import LineMap from './LineMap'
import { getLineMapData } from '../../../data/maps/LineMapData'

export default {
  name: 'line-maps-page',
  components: {
    LineMap,
  },
  data () {
    return {
      images: [
        'https://i.imgur.com/qSykGko.jpg',
        'https://i.imgur.com/jYwT08D.png',
        'https://i.imgur.com/9930myH.jpg',
        'https://i.imgur.com/2JxhWD6.jpg',
        'https://i.imgur.com/MpiOWbM.jpg',
        'data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAgGBgcGBQgHBwcJCQgKDBQNDAsL%0ADBkSEw8UHRofHh0aHBwgJC4nICIsIxwcKDcpLDAxNDQ0Hyc5PTgyPC4zNDL/%0A2wBDAQkJCQwLDBgNDRgyIRwhMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIy%0AMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjL/wAARCAArAVkDASIAAhEBAxEB/8QA%0AHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUF%0ABAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkK%0AFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1%0Adnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXG%0Ax8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEB%0AAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAEC%0AAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRom%0AJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOE%0AhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU%0A1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD1B5vHsiYW%0A00ONv7wuJD/7LTnPjYW+Fj0jzio+YyvjP/fNdV7dQKM4oA5ZrXxkzrJ/aNio%0AC/NGI8gt9dtRS2PjeWFyuqWFs/8ACqRBgfxIrrd3qPw4pc4IoA5FNO8atasH%0A120WfjBW3Uj+VOfSPGW/5PEsITj/AJc0P9K63PHWjrQBzC6L4pYtv8Vbc9Nt%0AjGf50o0LxL/0OMn/AIL4q6ak3ZAx3oA5v+wfEx/5nGT/AMF8VH9heJv+hxk/%0A8F0NdJnPT86M+1AHN/2F4m/6HGT/AMF0NH9heJv+hxk/8F0NdKOaUnaM/nQB%0AzQ0LxN/0OEn/AILoaP7D8Tf9DfJ/4Loq6MMQBuHPTjpS7vQg0Ac3/YfiP/ob%0ApM/9eEVL/YXiPv4tk/8AACKuizyemM0ZoA53+w/EI/5m2T/wBipn/CO643zN%0A4pm3eq2qCumz19fSjJoA5RfCmqgkt4puyT/0xUf1pT4Qu2+/4hvm+ny/yNdT%0Ak5oP4UAcj/wgpOM65qXH/TVh/WgeAY8DOtaqcf8ATy4/rXXZOORxRk9MZ/Cg%0ADk/+EBtBy2qaqx/6/JB/Wpx4G0sDDXeqE+v2+Uf1rpTyPWo1mSUnayOFOCQ3%0ARh2oA5w+AtIzn7Rquf8AsJTf/FUN4D0fb81zqwH/AGEpv/iq6IXMUkXnLIjR%0AjndngUqSpMoZGDowzlf5UAc1/wAIDo//AD8avj/sJTf/ABVKfAGjAZ+06sP+%0A4lN/8VXQXF3BZxebcTRxRnADyMAMngD86SS7gieKKaaINMdsYLDLt6CgDB/4%0AQLSAP+PjVj/3Epv/AIqj/hBNIzzPq3/gym/+KrpAx4yMDH5exqCDULW4SSWC%0AeKVEJV2RwQuOufSgDCPgTSBj9/qp/wC4lN/8VSjwHo5GfP1X/wAGU3/xVdBb%0AzxXMK3EDo8cigo6HIYHvUoOBgd/SgDmj4E0cHmfVf/BlN/8AFUjeA9HI5m1Q%0A/wDcRm/+KrZutZ03Tztu9QtoH9JpVU/TrVtWDkMpGCM5HII9jQBzJ8A6EwG9%0AtQcdt19Kf/ZqcfAGgNy8Ny+P79y5/rW/cXsFn5TXE0cSyuI08w4BY9APyqYE%0AuASMe/8AnrQBzJ+H/h0H/j0k5/6bN/jUy+BfDyN/x4Fsf3pGP9a1JtX0+GWW%0AGW+to3hIEivIFK5wR1+opj69pKBg2qWS7epadRj9aAKQ8G+Hw+Bp0ZPpinf8%0AId4e/wCgVbnHqgNa8F1FcxLLbyJNG33XRsg/jVe01K1uru4ggnDyW5AlUds8%0A/wBKAKsPhXQIQSmkWZz/AHoVP9KcPDOhb9w0fT/p9mT/AAqxe6pbWEtslxJ5%0AZuH8tAe5xmrwPYUAcN4T0TSp77xKJdKsHEWryRpm2T5V8tDjp710/wDwjeh/%0A9AXTv/AVP8KyPBv/ACEPFP8A2GJP/RcddXQBGwOML+fvXnFzruvvd3sVtfP/%0AAKLcXkcoSFWCKkW9DnHcnFejMmQAThQORXkN/qqW2q61ZW8dy13Jf3YeOOMl%0AJUMK5ye5Uc4oAsT+N3HhFLqDxSzamkaFoltMhmyARkr713HiHXX0KxtZIoxc%0A3M0yIsO4K0oONxGSBkdeuK85ubCY6HbaYl7qs8upxBdPTzSsKMuMpIcY5IJ/%0ACur8WpcyeFNLN/Zac2qzXVvaObiESxxNIwViBkZHPrQMreEvFl0bBEu9O1E+%0AY8xF1M8XljG44+9nHGOnWrllrc+oeI/DV2HeGPUbCeWS2JHzFdmD19zXF6do%0AMWmzaPb3EWh3i3t3cQtGLALKoCyNkNuOOV9O9dRpC41nwMBEUxpdz8vTbxHx%0AigCx4v1W8vydD0IuZYXWW9mQkeRGp3YB4y3Tjpg1BB4j1DXtd0y38Nap9qtY%0A2E2pPJGv7tO0Z44Yg54/u1neKm1fQhHHcpFd213cAD7DcCxeV2OPLZcN5g2n%0Ak+grl7PTdSsba9j060m025nu54I7mPV1gjV0baEIK/MRnA6Z5oA9j8SatBoP%0Ahy/vZ5PKSOFgrHoHwdo/EkVwlprVzY6bDpV1qEkwk0qS6uJepSWQq6DI5GAS%0ABWzeeFpbfwZIuq6ncanNb2k8ztK3E0vlkZI54HBAz19aqWGgasnhmO/sNTtL%0AaK9023aVJrXe3yxAY3bhQBo+CvEHm6LodiyXFxLLaea9yBlE68EnqatzeINT%0ATULy28/RlFpgyhpJd0YOCMjHXB7VjeCdO8Rnw1o0i65anTxEP3Js9zFc85bd%0A6e1V9QudOj13xG8upaOGvkRITcXaqyEIFPHUdKAKk1zqmo6/rNzHfWMNrFaW%0A16lws0pRAC5DAY5zg7h9K7Nr7Vrfw7Bf3lxYIyL5lzJEzbGTHBUkdTxXnF4i%0AW9tpOmG4MX2u3t7DU5WOzy4kztKnuH3Ng98V6XPpul65bR2P2h5bazwrxRS/%0AK+Fwqv8A3scN9QDQBxOp6xfaq19r0bX1vFoVkl7bwsNpud6lsMBxj5eO/rXT%0A6fq8t/rVtA+qyRSqA8llJCo80FM8HHTJ/SuM8V6ZpfhrUroazqmry2eoWojj%0ARbwhpNgwUk4OQcgA9q67wd4alt9KsbrVryXULyJzLbvLL5ogBG0Kp/3aAKl3%0ANq1r4yt9Pk8VOLO5SSVFMMIKspGIwQOmCevPFYOm6ubnwzDYubuW6k0aa6e5%0AEpHl48zaTyOcrVyeLRNQ8e50nRIr5reKdLl0i2xeeWBXL9M8HP1rE0mK8S+t%0AdNt57c28unnR7idk3J5oLMQh7qBIOaAPSrCbVZPCGjy6aLaW4ktYTIbt2AwU%0A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%0Ax/8AiX/sKt/6LSuooA//2Q==',
      ],
    }
  },
  computed: {
    lineMapData () {
      return getLineMapData(this.$themes)
    },
  },
}
</script>
