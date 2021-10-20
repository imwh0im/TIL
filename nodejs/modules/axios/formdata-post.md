# Formdata POST

- axios 를 이용해서 `formdata` POST 하기
  + `query-string` 모듈 이용하기
    ```typescript
    import axios from 'axios';
    import queryString from 'query-string'

    const formData = {
      hello: 'world',
      great: 'henry',
    };

    const res = axios({
      method: 'POST',
      url: 'https://sample.com',
      data: queryString.stringify(formData);
    })

    ```

  + formData 객체 선언해서 하기
    ```typescript
    import axios from 'axios';

    const formData = new FormData();

    formData.append('hello', 'world');
    formData.append('great', 'henry');

    const res = axios({
      method: 'POST',
      url: 'https://sample.com',
      data: formData;
    });
    ```