# 에디터 (Editor)

> 실행예제
http://makeapi.net/test/editor.html  

> 정리자료  
http://makestory.net/media/#/view/201  

-----
  
````javascript
// 텍스트 에디터
api.editor.setup({
	'key': 'textedit', // 에디터 key
	'type': 'text', // 에디터 type
	'target': '#editor', // 에디터 적용 element
	'tooltip': true, // 툴팁 사용여부
	'classes': {
		'link': 'editor-text-link' // a 태그에 적용될 class 속성값
	},
	'listeners': { 
		'init': null
	}
}).on();

// 이미지/동영상(작업중) 에디터
api.editor.setup({
	'key': 'multiedit', // 에디터 key
	'type': 'multi', // 에디터 type
	'target': '#editor', // 에디터 적용 element
	'image': true, // 이미지 사용여부
	'video': true, // 비디오 사용여부
	'code': true, // 코드 사용여부
	'line': true, // 구분선 사용여부
	'tooltip': {
		'image': {
			'put': true, // 이미지 넣기 툴팁 보이기 / 숨기기
			'location': true // 이미지 위치 수정 툴팁 보이기 / 숨기기
		}
	},
	'size': {
		'image': {
			'min': {
				'width': 0,
				'height': 0
			},
			'max': {
				'width': 0,
				'height': 0
			}
		}
	},
	'submit': {
		'image': '//makestory.net/files/editor', // 이미지 파일 전송 url
	},
	// element 에 설정할 class 속성값
	'classes': {
		'image': {
			'wrap': 'editor-image-wrap', // 이미지 감싸는 element
			'wide': 'editor-image-wide', // 이미지 와이드
			'left': 'editor-image-wrap-left', // 이미지 왼쪽 글자 오른쪽
			'right': 'editor-image-wrap-right', // 이미지 오른쪽 글자 왼쪽
			'figure': 'editor-image-figure', // img 태그 감싸는 element
			'img': 'editor-image-img',
			'figcaption': 'editor-image-figcaption'
		},
		'code': {
			'wrap': 'editor-code-wrap'
		}
	},
	'listeners': {
		'init': null
	}
}).on();

// 오픈그래프 (링크 meta 출력)
api.editor.setup({
	'key': 'opengraph',
	'type': 'opengraph',
	'submit': '//makestory.net/opengraph', // link url 정보를 받아 meta 정보를 돌려줄 서버측 url
	'classes': {
		'wrap': 'opengraph-wrap',
		'image': 'opengraph-image',
		'text': 'opengraph-text',
		'title': 'opengraph-title',
		'description': 'opengraph-description',
		'author': 'opengraph-author'
	},
	'listeners': {
		'init': null
	}
}).on();

// 서버측 오픈그래프 return json 구조
{
	'status': 'success', 
	'result': {
		'title': '페이지 제목',
		'description': '페이지 요약',
		'image': '이미지',
		'author': '원작자',
		'keywords': '키워드'
	}
}

// 해당요소 에디터 해제
api.editor.search('에디터키').off();
```