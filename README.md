# PSR-7 interfaces

This repository holds all interfaces related to [PSR-7](http://www.php-fig.org/psr/psr-7/). This's fork of 
 [php-fig/http-message](https://github.com/php-fig/http-message) except usage of strict types. All interface methods 
 have strict type declarations. 
 
For example, if `Psr\Http\RequestInterface` is defined like

```php
interface RequestInterface extends MessageInterface {
    /**
     * @return string
     */
    public function getRequestTarget();

    /**
     * @param mixed $requestTarget
     * @return self
     */
    public function withRequestTarget($requestTarget);

    /**
     * @return string Returns the request method.
     */
    public function getMethod();

    /**
     * @param string $method Case-sensitive method.
     * @return self
     * @throws InvalidArgumentException for invalid HTTP methods.
     */
    public function withMethod($method);

    /**
     * @return UriInterface Returns a UriInterface instance representing the URI of the request.
     */
    public function getUri();

    /**
     * @param UriInterface $uri New request URI to use.
     * @param bool $preserveHost Preserve the original state of the Host header.
     * @return self
     */
    public function withUri(UriInterface $uri, $preserveHost = false);
}
```
 
...then `alxmsl\Psr7\RequestInterface` will be defined like

```php
interface RequestInterface extends MessageInterface {
    /**
     * @return string
     */
    public function getRequestTarget(): string;

    /**
     * @param mixed $requestTarget
     * @return self
     */
    public function withRequestTarget(mixed $requestTarget): RequestInterface;

    /**
     * @return string Returns the request method.
     */
    public function getMethod(): string;

    /**
     * @param string $method Case-sensitive method.
     * @return self
     * @throws InvalidArgumentException for invalid HTTP methods.
     */
    public function withMethod(string $method): RequestInterface;

    /**
     * @return UriInterface Returns a UriInterface instance representing the URI of the request.
     */
    public function getUri(): UriInterface;

    /**
     * @param UriInterface $uri New request URI to use.
     * @param bool $preserveHost Preserve the original state of the Host header.
     * @return self
     */
    public function withUri(UriInterface $uri, bool $preserveHost = false): RequestInterface;
}
```

## License

Copyright 2016 Alexey Maslov <alexey.y.maslov@gmail.com>

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

