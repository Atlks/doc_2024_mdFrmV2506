Go query coll




func TestHandler_qry(t *testing.T) {
    // rcd:={"id":1};

    rcd := map[string]any{
       "id":   1,
       "name": "name111",
    }

    rcd2 := map[string]any{
       "id":   2,
       "name": "name222",
    }

    var arr []any

    //追加一个元素
    arr = append(arr, rcd, rcd2)

    rows := Filter(arr,
       func(v any) bool {

          map1 := v.(map[string]any)
          map1 = AnyToMap(v)
          if map1["id"] == 1 {
             return true
          } else {
             return false
          }

       },
    )

    print(rows)
    //Pdo_Insert(rcd, "coll33", "c:/dbx/")
}




func Filter[T any](slice []T, f func(T) bool) []T {
    var n []T
    for _, e := range slice {
       if f(e) {
          n = append(n, e)
       }
    }
    return n
}

