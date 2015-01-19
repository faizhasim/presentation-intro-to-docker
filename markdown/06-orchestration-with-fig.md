# Orchestration with [Fig](fig.sh)


---

`touch fig.yml`


---

```yaml
helloworld:
  build: helloworld/.
  ports:
    - "80:3000"
```

---


`fig build`

---

`fig up`

