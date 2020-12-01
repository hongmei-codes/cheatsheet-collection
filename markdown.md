<div align="center">
  <br>
  <h1>Markdown Cheatsheet  📗</h1>
  <strong>a quick reference</strong>
</div>
<br>

---

```markdown
# hello
```
# hello

---

```markdown
__hello__ _hello_ ~hello~
```

__hello__ _hello_ ~hello~

---

```markdown
> hello
```

> hello

---
`[hello](https://hello.com)`

[hello](https://hello.com)

---
```markdown
* hello
- hello
	* hello
		- hello
			* hello
```

* hello
- hello
	* hello
		- hello
			* hello

---
```markdown
1. hello
2. hello
```
1. hello
2. hello

---
```markdown
- [ ] hello
- [x] hello
```
- [ ] hello
- [x] hello

---
### console
```markdown
	```console
	$ git init
	```
```
```console
$ git init
```

### python
```markdown
	```python
	def hello(name):
		print('hello' + name)
	```
```
```python
def hello(name):
	print('hello' + name)
```

---
```markdown
| hello | hello | hello |
| --- | --- | --- |
| hello | hello | hello |
| hello | hello | hello |
| hello | hello | hello |
```
| hello | hello | hello |
| --- | --- | --- |
| hello | hello | hello |
| hello | hello | hello |
| hello | hello | hello |

<table>
<tr>
<th>do ✅</th><th>don't ⛔️</th>
</tr>
<tr>
<td>

```json
{
"id": 10,
"username": "alanpartridge",
"email": "alan@alan.com",
"password_hash": "$2a$10",
"password_salt": "$2a$10",
"created_at": "2015-02-14T20:45:26.433Z",
"updated_at": "2015-02-14T20:45:26.540Z"
}
```
</td>
<td>

```json
{
"id": 10,
"username": "alanpartridge",
"email": "alan@alan.com",
"password_hash": "$2a$10",
"password_salt": "$2a$10",
"created_at": "2015-02-14T20:45:26.433Z",
"updated_at": "2015-02-14T20:45:26.540Z"
}
```
</td>
</tr>
</table>

```html
<table>
<tr>
<th>do ✅</th><th>don't ⛔️</th>
</tr>
<tr>
<td>

\`\`\`json
{
"id": 10,
"username": "hi",
}
\`\`\`
</td>
<td>

\`\`\`json
{
"id": 10,
"username": "hey"
}
\`\`\`
</td>
</tr>
</table>
```

---
```markdown
<details><summary>Click to expand</summary>

- [skip to hello on top](#hello)
- [some link](https://google.com)
- [some other link](https://google.com)
  - [some sub link](https://google.com)
    - [sub sub link](https://google.com)
  - [some other sub link](https://google.com)

</details>
```
<details><summary>Click to expand</summary>

- [skip to hello on top](#hello)
- [some link](https://google.com)
- [some other link](https://google.com)
  - [some sub link](https://google.com)
    - [sub sub link](https://google.com)
  - [some other sub link](https://google.com)

</details>

---
