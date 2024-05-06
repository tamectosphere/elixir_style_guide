# [The Elixir Style Guide][Elixir Style Guide]

## สารบัญ

* __[บทนำ](#บทนำ)__
* __[เกี่ยวกับ](#เกี่ยวกับ)__
* __[การจัดเรียง (Formatting)](#formatting)__
  * [การเว้นช่องว่าง (whitespace)](#whitespace)
  * [การย่อหน้า (Indentation)](#indentation)
  * [การใส่วงเล็บ (Parentheses)](#parentheses)
* __[คู่มือ](#คู่มือ)__
  * [นิพจน์ (Expressions)](#expressions)
  * [การตั้งชื่อ (Naming)](#naming)
  * [การใส่คอมเมนต์ (Comments)](#comments)
    * [การใส่คำอธิบายประกอบ (Comments Annotations)](#comment-annotations)
  * [โมดูล (Modules)](#modules)
  * [การเขียนเอกสารกำกับโปรแกรม (Documentation)](#documentation)
  * [การเขียนไทป์สเปค (Typespecs)](#typespecs)
  * [สตรัค (Structs)](#structs)
  * [การจัดการกับข้อผิดพลาด (Exceptions)](#exceptions)
  * [คอลเลกชัน (Collections)](#collections)
  * [สตริง (Strings)](#strings)
  * _นิพจน์ปรกติ (Regular Expressions)_
  * [เมต้าโปรแกรมมิ่ง (Metaprogramming)](#metaprogramming)
  * [การทดสอบโปรแกรม (Testing)](#testing)
* __[แหล่งที่มา (Resources)](#resources)__
  * [คู่มืออื่นๆ (Alternative Style Guides)](#alternative-style-guides)
  * [เครื่องมือ (Tools)](#tools)
* __[เข้ามามีส่วนร่วมกับเรา](#getting-involved)__
  * [การสนับสนุน (Contributing)](#contributing)
  * [เผยแพร่ข่าวสาร (Spread the Word)](#spread-the-word)
* __[การก๊อปปี้ (Copying)](#copying)__
  * [ลิขสิทธิ์ (License)](#license)
  * [การยกเครดิต (Attribution)](#attribution)

## บทนำ

> สถาปัตยกรรมเต็มไปด้วยพลังและความคิดสร้างสรรค์ มันก็เหมือนกับดนตรีแจ๊ส — คุณประพันธ์และด้นสดบทเพลงขึ้นมาใหม่ เชื่อมโยงศาสตร์และศิลป์กับนักดนตรีคนอื่นๆโดยใช้สัญชาตญาณ และตอบสนองต่อการแสดงออกทางดนตรีซึ่งกันและกันได้อย่างลื่นไหล ในท้ายที่สุดผลงานที่ออกมาจะมีความเป็นธรรมชาติและตอบสนองต่อผู้ฟังมากกว่า ซึ่งสะท้อนถึงความคิดสร้างสรรค์โดยรวมและการมีปฏิสัมพันธ์ของนักออกแบบเป็นที่ตั้ง
>
> —Frank Gehry

รูปแบบของการเขียนโค้ดนั้นเป็นเรื่องสำคัญ เช่นเดียวกันกับ
[Elixir] ที่ไม่มีรูปแบบของการเขียนที่ตายตัวแต่มันสามารถถูกจำกัดตามวิธีการใช้งานเหมือนกับ programming language อื่นๆ แต่อย่างไรก็ตามเราไม่ควรที่จะให้ข้อจำกัดมากระทบต่อรูปแบบการเขียนของ Elixir

## เกี่ยวกับ

นี่คือ community ที่ให้คำแนะนำสำหรับ [Elixir programming language][Elixir] ที่จัดทำโดยเพื่อนๆที่รักในการเขียน Elixir คุณสามารถไปเปิด pull request เพื่อแนะนำหรือเปลี่ยนแปลงเพิ่มเติมได้ ขอเชิญร่วมมาเป็นส่วนหนึ่งของ Elixir community ด้วยกันครับ

ถ้าคุณต้องการที่จะ contribute ให้กับ project อื่นๆ สามารถเข้าไปดูในนี้ได้ครับ
[Hex package manager site][Hex].

<a name="translations"></a>
ส่วนคู่มือในภาษาอื่นๆนั้น สามารถเลือกดูข้างล่างได้เลยครับ:

* [Chinese Simplified] (จีนตัวย่อ)
* [Chinese Traditional] (จีนดั้งเดิม)
* [French] (ฝรั่งเศส)
* [Japanese] (ญี่ปุ่น)
* [Korean] (เกาหลี)
* [Portuguese] (โปรตุเกส)
* [Russian] (รัสเซีย)
* [Spanish] (สเปน) 
* [Thai] (ไทย) 

<h2 id="formatting">การจัดเรียง (Formatting)</h2>

Elixir ตั้งแต่เวอร์ชั่น 1.6 ขึ้นไป ได้นำ [Code Formatter] และ [Mix format] มาใช้ ซึ่งเราควรเอาตัว Formatter มาใช้ในทุกๆ project เช่นกัน

นี่เป็นตัวอย่างรูปแบบที่ใช้กัน ซึ่งปกติแล้วตัว formatter มันจะทำให้เราอัตโนมัติอยู่แล้วครับ

<h3 id="Whitespace">การเว้นช่องว่าง (whitespace)</h3>

* <a name="trailing-whitespace"></a>
  หลีกเลี่ยงการเว้นช่องว่าง(whitespace) ที่ไม่จำเป็นไว้ในตอนท้ายบรรทัดในโค้ด
  <sup>[[link](#trailing-whitespace)]</sup>

* <a name="newline-eof"></a>
  ตัดจบไฟล์ทุกไฟล์ด้วยการขึ้นบรรทัดใหม่.
  <sup>[[link](#newline-eof)]</sup>

* <a name="line-endings"></a>
  ใช้การจบบรรทัดแบบ Unix-style (ผู้ใช้ BSD/Solaris/Linux/OSX มีการตั้งค่านี้เป็นค่าเริ่มต้นอยู่แล้ว ส่วนผู้ใช้ Windows ควรต้องระวังเป็นพิเศษ)
  <sup>[[link](#line-endings)]</sup>

* <a name="autocrlf"></a>
  ถ้าหากหากคุณกำลังใช้ Git อยู่ คุณอาจต้องการเพิ่มการตั้งค่า config นี้เพื่อป้องกันไม่ให้ Windows line endings แทรกเข้ามาในโปรเจกต์ของคุณ:
  <sup>[[link](#autocrlf)]</sup>

  ```sh
  git config --global core.autocrlf true
  ```

* <a name="line-length"></a>
 จำกัดความยาวของแต่ละบรรทัดไม่เกิน 98 ตัวอักษร หากต้องการกำหนดค่าตัวอักษรที่แตกต่างจากนี้ ให้ตั้งค่า `:line_length` ในไฟล์ `.formatter.exs` ของคุณ
  <sup>[[link](#line-length)]</sup>

* <a name="spaces"></a>
  ใช้ช่องว่างรอบๆ ตัว operators, หลังจาก commas, colons, และ semicolons อย่าใส่ช่องว่างรอบๆ พวกคู่วงเล็บ, วงเล็บเหลี่ยม หรืออื่นๆ แม้ว่า whitespace อาจไม่สำคัญมากสำหรับรันไทม์ของ Elixir แต่การใช้งานอย่างถูกต้องเป็นกุญแจสำคัญในการเขียนโค้ดที่อ่านง่าย
  <sup>[[link](#spaces)]</sup>

  ```elixir
  sum = 1 + 2
  {a, b} = {2, 3}
  [first | rest] = [1, 2, 3]
  Enum.map(["one", <<"two">>, "three"], fn num -> IO.puts(num) end)
  ```

* <a name="no-spaces"></a>
  อย่าใช้ช่องว่างหลังจาก non-word operators ที่รับค่าจริงเพียงหนึ่งตัว; หรือรอบ ๆ range operator
  <sup>[[link](#no-spaces)]</sup>

  ```elixir
  0 - 1 == -1
  ^pinned = some_func()
  5 in 1..10
  ```

* <a name="def-spacing"></a>
  ใช้บรรทัดว่างระหว่าง `def` เพื่อแบ่งฟังก์ชันออกเป็นส่วนๆตาม logic
  <sup>[[link](#def-spacing)]</sup>

  ```elixir
  def some_function(some_data) do
    some_data |> other_function() |> List.first()
  end

  def some_function do
    result
  end

  def some_other_function do
    another_result
  end

  def a_longer_function do
    one
    two

    three
    four
  end
  ```

* <a name="defmodule-spacing"></a>
  อย่าใส่บรรทัดว่างหลังจาก `defmodule`
  <sup>[[link](#defmodule-spacing)]</sup>

* <a name="long-dos"></a>
  หากหัวของ function และ `do:` clause ยาวเกินกว่าจะอยู่ในบรรทัดเดียวกันได้ ให้วาง `do:` ไว้ในบรรทัดใหม่ โดยเว้นย่อหน้าเพิ่มขึ้นหนึ่งระดับจากบรรทัดก่อนหน้า
  <sup>[[link](#long-dos)]</sup>

  ```elixir
  def some_function([:foo, :bar, :baz] = args),
    do: Enum.map(args, fn arg -> arg <> " is on a very long line!" end)
  ```

  เมื่อ `do:` clause เริ่มต้นบนบรรทัดของตัวเอง ควรจัดการมันเหมือนกับ function ที่มีหลายบรรทัด โดยการแยกมันด้วยการใช้บรรทัดว่าง

  ```elixir
  # ไม่แนะนำ
  def some_function([]), do: :empty
  def some_function(_),
    do: :very_long_line_here

  # แนะนำ
  def some_function([]), do: :empty

  def some_function(_),
    do: :very_long_line_here
  ```

* <a name="add-blank-line-after-multiline-assignment"></a>
  เพิ่มบรรทัดว่างหลังจากการกำหนดค่าตัวแปรที่ต้องทำหลายบรรทัด เพื่อให้เป็นตัวบอกว่าการกำหนดค่าให้กับตัวแปรนั้น ‘เสร็จสิ้น’ แล้ว
  <sup>[[link](#add-blank-line-after-multiline-assignment)]</sup>

  ```elixir
  # ไม่แนะนำ
  some_string =
    "Hello"
    |> String.downcase()
    |> String.trim()
  another_string <> some_string

  # แนะนำ
  some_string =
    "Hello"
    |> String.downcase()
    |> String.trim()

  another_string <> some_string
  ```

  ```elixir
  # ไม่แนะนำเช่นกัน
  something =
    if x == 2 do
      "Hi"
    else
      "Bye"
    end
  String.downcase(something)

  # แนะนำ
  something =
    if x == 2 do
      "Hi"
    else
      "Bye"
    end

  String.downcase(something)
  ```

* <a name="multiline-enums"></a>  
  
  ถ้าเป็น list, map, หรือ struct ที่สามารถขยายออกมาเป็นหลายบรรทัด ให้วางแต่ละ element รวมถึงวงเล็บเปิดและปิดในบรรทัดของตัวเอง ขยับแต่ละ element ให้มีการเยื้องหนึ่งระดับโดยไม่เยื้องกับวงเล็บ
  <sup>[[link](#multiline-enums)]</sup>

  ```elixir
  # ไม่แนะนำ
  [:first_item, :second_item, :next_item,
  :final_item]

  # แนะนำ
  [
    :first_item,
    :second_item,
    :next_item,
    :final_item
  ]
  ```

* <a name="multiline-list-assign"></a>
  เมื่อต้องกำหนดค่าให้กลับตัวแปรที่เป็น list, map, หรือ struct ควรให้วงเล็บเปิดอยู่ที่บรรทัดเดียวกันกับที่ตัวแปรถูกประกาศ
  <sup>[[link](#multiline-list-assign)]</sup>

  ```elixir
  # ไม่แนะนำ
  list =
  [
    :first_item,
    :second_item
  ]

  # แนะนำ
  list = [
    :first_item,
    :second_item
  ]
  ```

* <a name="multiline-case-clauses"></a>

  เวลาเขียน `case` หรือ `cond` clause ถ้ามันมีมากกว่าหนึ่งบรรทัด (เนื่องจากความยาวของบรรทัด, expressions หลายตัวหรืออื่นๆ) ให้ใช้ multi-line syntax สำหรับ clause ทั้งหมด และแยกแต่ละ clause ด้วยบรรทัดว่าง
  <sup>[[link](#multiline-case-clauses)]</sup>

  ```elixir
  # ไม่แนะนำ
  case arg do
    true -> IO.puts("ok"); :ok
    false -> :error
  end

  # ไม่แนะนำ
  case arg do
    true ->
      IO.puts("ok")
      :ok
    false -> :error
  end

  # แนะนำ
  case arg do
    true ->
      IO.puts("ok")
      :ok

    false ->
      :error
  end
  ```

* <a name="comments-above-line"></a>
  
  ให้ใส่ comment ไว้ด้านบนของบรรทัดที่เกี่ยวข้องเสมอ
  <sup>[[link](#comments-above-line)]</sup>

  ```elixir
  String.first(some_string) # ไม่แนะนำ

  # แนะนำ
  String.first(some_string)
  ```

* <a name="comment-leading-spaces"></a>

  เวลาเขียน comment หลังจากที่พิมพ์ `#` แล้ว ให้เว้นช่องว่างไว้หนึ่งช่องแล้วจึงค่อยใส่ข้อความตามมา 
  <sup>[[link](#comment-leading-spaces)]</sup>

  ```elixir
  #ไม่แนะนำให้เขียนข้อความติดกับตัว `#`
  String.first(some_string)

  # แนะนำ
  String.first(some_string)
  ```

<h3 id="indentation">การย่อหน้า (Indentation)</h3>

* <a name="with-clauses"></a>
  ย่อหน้าและจัดแนวของ `with` clauses ที่ต่อเนื่องกัน ควรวาง argument ของ `do:` บนบรรทัดใหม่ จัดแนวให้ตรงกับ clauses ก่อนหน้านี้
  <sup>[[link](#with-clauses)]</sup>

  ```elixir
  with {:ok, foo} <- fetch(opts, :foo),
       {:ok, my_var} <- fetch(opts, :my_var),
       do: {:ok, foo, my_var}
  ```

* <a name="with-else"></a>

  ถ้าหาก `with` expression มี `do` ที่มีมากกว่าหนึ่งบรรทัด หรือมีตัวเลือก else ให้ใช้ multiline syntax
  <sup>[[link](#with-else)]</sup>

  ```elixir
  with {:ok, foo} <- fetch(opts, :foo),
       {:ok, my_var} <- fetch(opts, :my_var) do
    {:ok, foo, my_var}
  else
    :error ->
      {:error, :bad_arg}
  end
  ```

<h3 id="parentheses">การใส่วงเล็บ (Parentheses)</h3>

* <a name="parentheses-pipe-operator"></a>
  เมื่อใช้ pipe operator (`|>`) ให้ใส่วงเล็บสำหรับฟังก์ชันที่มีรับตัวแปร 1 ตัว 
  <sup>[[link](#parentheses-pipe-operator)]</sup>

  ```elixir
  # ไม่แนะนำ
  some_string |> String.downcase |> String.trim

  # แนะนำ
  some_string |> String.downcase() |> String.trim()
  ```

* <a name="function-names-with-parentheses"></a>
  อย่าใส่ช่องว่างระหว่างชื่อฟังก์ชันและวงเล็บเปิด
  <sup>[[link](#function-names-with-parentheses)]</sup>

  ```elixir
  # ไม่แนะนำ
  f (3 + 2)

  # แนะนำ
  f(3 + 2)
  ```

* <a name="function-calls-and-parentheses"></a>
  ใช้วงเล็บในการเรียกฟังก์ชัน โดยเฉพาะใน pipeline operator.
  <sup>[[link](#function-calls-and-parentheses)]</sup>

  ```elixir
  # ไม่แนะนำ
  f 3

  # แนะนำ
  f(3)

  # ไม่แนะนำ ตัวโปรแกรมจะเข้าผิดว่าเป็นฟังก์ชัน rem(2, (3 |> g)) แทน
  2 |> rem 3 |> g

  # แนะนำ
  2 |> rem(3) |> g()
  ```

* <a name="keyword-list-brackets"></a>
  ละเว้นการใส่ square brackets จาก keyword lists เมื่อไม่จำเป็นต้องใช้
  <sup>[[link](#keyword-list-brackets)]</sup>

  ```elixir
  # ไม่แนะนำ
  some_function(foo, bar, [a: "baz", b: "qux"])

  # แนะนำ
  some_function(foo, bar, a: "baz", b: "qux")
  ```

## คู่มือ

หลักการต่างๆในส่วนนี้อาจไม่ถูกใช้โดย code formatter แต่โดยทั่วไปแล้วเป็นสิ่งที่แนะนำ

<h3 id="expressions">นิพจน์ (Expressions)</h3>

* <a name="single-line-defs"></a>

  ให้นำ `def` ที่รันแบบบรรทัดเดียวเอามาติดกันกับฟังก์ชันเดียวกัน ส่วน `def` ที่มีหลายบรรทัดให้แยกกันด้วยบรรทัดว่าง
  <sup>[[link](#single-line-defs)]</sup>

  ```elixir
  def some_function(nil), do: {:error, "No Value"}
  def some_function([]), do: :ok

  def some_function([first | rest]) do
    some_function(rest)
  end
  ```

* <a name="multiple-function-defs"></a>
  อย่าใช้ `def` แบบบรรทัดเดียว ถ้าหากคุณมี `def` แบบหลายบรรทัดมากกว่าหนึ่งตัว 
  <sup>[[link](#multiple-function-defs)]</sup>

  ```elixir
  def some_function(nil) do
    {:error, "No Value"}
  end

  def some_function([]) do
    :ok
  end

  def some_function([first | rest]) do
    some_function(rest)
  end

  def some_function([first | rest], opts) do
    some_function(rest, opts)
  end
  ```

* <a name="pipe-operator"></a>
  ใช้ pipe operator เพื่อเชื่อมฟังก์ชันเข้าด้วยกัน
  <sup>[[link](#pipe-operator)]</sup>

  ```elixir
  # ไม่แนะนำ
  String.trim(String.downcase(some_string))

  # แนะนำ
  some_string |> String.downcase() |> String.trim()

  # Multiline pipelines ไม่ต้องย่อหน้าเพิ่ม
  some_string
  |> String.downcase()
  |> String.trim()

  # Multiline pipelines อยู่ที่ข้างขวาของ pattern match
  # ควรต้องย่อหน้าเมื่อขึ้นบรรทัดใหม่
  sanitized_string =
    some_string
    |> String.downcase()
    |> String.trim()
  ```

  ถึงแม้ว่านี่จะเป็นวิธีที่แนะนำ แต่มันมีปัญหาเมื่อเราทำการคัดลอกและวาง multiline pipelines ลงใน IEx ซึ่งอาจจะทำให้เกิด syntax error เนื่องจาก IEx จะประมวลผลบรรทัดแรกโดยไม่รู้ว่าบรรทัดถัดไปมี pipeline อยู่ เพื่อหลีกเลี่ยงปัญหานี้ คุณสามารถใช้วิธีเอามฟังก์ชันใส่เอาไว้ในวงเล็บแทน ตัวอย่างเช่น

   ```elixir
  String.trim(String.downcase(some_string))
  ```

* <a name="avoid-single-pipelines"></a>
  หลีกเลี่ยงการใช้ pipe operator เพียงครั้งเดียว
  <sup>[[link](#avoid-single-pipelines)]</sup>

  ```elixir
  # ไม่แนะนำ
  some_string |> String.downcase()

  System.version() |> Version.parse()

  # แนะนำ
  String.downcase(some_string)

  Version.parse(System.version())
  ```

* <a name="bare-variables"></a>
  ใช้ตัวแปรเพียวๆในส่วนแรกของ function chain
  <sup>[[link](#bare-variables)]</sup>

  ```elixir
  # ไม่แนะนำ
  String.trim(some_string) |> String.downcase() |> String.codepoints()

  # แนะนำ
  some_string |> String.trim() |> String.downcase() |> String.codepoints()
  ```

* <a name="fun-def-parentheses"></a>
  ถ้า `def` รับ arguments มาให้ใส่วงเล็บ ถ้าไม่มีไม่ต้องใส่วงเล็บ
  <sup>[[link](#fun-def-parentheses)]</sup>

  ```elixir
  # ไม่แนะนำ
  def some_function arg1, arg2 do
    # body omitted
  end

  def some_function() do
    # body omitted
  end

  # แนะนำ
  def some_function(arg1, arg2) do
    # body omitted
  end

  def some_function do
    # body omitted
  end
  ```

* <a name="do-with-single-line-if-unless"></a>
  ใช้ `do:` สำหรับ `if/unless` แบบบรรทัดเดียว
  <sup>[[link](#do-with-single-line-if-unless)]</sup>

  ```elixir
  # แนะนำ
  if some_condition, do: # ใส่ logic บางอย่าง ถ้าเข้าเงื่อนไขใน if
  ```

* <a name="unless-with-else"></a>
  อย่าใช้ `unless` ร่วมกับ `else` ให้เขียนใหม่โดย `if` ก่อน
  <sup>[[link](#unless-with-else)]</sup>

  ```elixir
  # ไม่แนะนำ
  unless success do
    IO.puts('failure')
  else
    IO.puts('success')
  end

  # แนะนำ
  if success do
    IO.puts('success')
  else
    IO.puts('failure')
  end
  ```

* <a name="true-as-last-condition"></a>
  สำหรับ `cond` ให้ใช้ `true` ไว้เป็นเงื่อนไขสุดท้ายในกรณีที่ไม่มีการเข้าเงื่อนไขไหนอะไรก่อนหน้านี้เลย
  <sup>[[link](#true-as-last-condition)]</sup>

  ```elixir
  # ไม่แนะนำ
  cond do
    1 + 2 == 5 ->
      "Nope"

    1 + 3 == 5 ->
      "Uh, uh"

    :else ->
      "OK"
  end

  # แนะนำ
  cond do
    1 + 2 == 5 ->
      "Nope"

    1 + 3 == 5 ->
      "Uh, uh"

    true ->
      "OK"
  end
  ```

* <a name="parentheses-and-functions-with-zero-arity"></a>

  ใช้วงเล็บเมื่อเรียกฟังก์ชันที่ไม่รับตัวแปร เพื่อให้แยกแยะจากตัวแปรได้ง่ายขึ้น เพราะตั้งแต่ Elixir 1.4 เป็นต้นไป compiler จะเตือนคุณเกี่ยวกับปัญหาไม่ชัดเจนนี้
  <sup>[[link](#parentheses-and-functions-with-zero-arity)]</sup>

  ```elixir
  defp do_stuff, do: ...

  #  ไม่แนะนำ
  def my_func do
    # ไม่รู้ว่าเป็นฟังก์ชันหรือตัวแปรกันแน่
    do_stuff
  end

  # แนะนำ
  def my_func do
    # เห็นได้ชัดว่านี้เป็นฟังก์ชัน
    do_stuff()
  end
  ```

<h3 id="naming">การตั้งชื่อ (Naming)</h3>

คู่มือนี้ถูกอ้างอิงมาจาก document ของ Elixir [Naming Conventions] ซึ่งรวมถึงการใช้ `snake_case` และ `CamelCase` เพื่ออธิบายหลักการในการตั้งชื่อ

* <a name="snake-case"></a>
  ใช้ snake_case สำหรับ atoms, ฟังก์ชัน, และตัวแปร
  <sup>[[link](#snake-case)]</sup>

  ```elixir
  # ไม่แนะนำ
  :"some atom"
  :SomeAtom
  :someAtom

  someVar = 5

  def someFunction do
    ...
  end

  # แนะนำ
  :some_atom

  some_var = 5

  def some_function do
    ...
  end
  ```

* <a name="camel-case"></a>
  ใช้ CamelCase สำหรับ modules (พวกตัวย่อเช่น HTTP, RFC, XML ให้ใช้เป็นตัวพิมพ์ใหญ่).
  <sup>[[link](#camel-case)]</sup>

  ```elixir
  # ไม่แนะนำ
  defmodule Somemodule do
    ...
  end

  defmodule Some_Module do
    ...
  end

  defmodule SomeXml do
    ...
  end

  # แนะนำ
  defmodule SomeModule do
    ...
  end

  defmodule SomeXML do
    ...
  end
  ```

* <a name="predicate-function-trailing-question-mark"></a>
  ฟังก์ชันที่คืนค่า boolean (`true` หรือ `false`) ควรตั้งชื่อโดยการนำเอาเครื่องหมายคำถามมาไว้ท้ายสุด
  <sup>[[link](#predicate-function-trailing-question-mark)]</sup>

  ```elixir
  def cool?(var) do
    String.contains?(var, "cool")
  end
  ```

* <a name="predicate-function-is-prefix"></a>
  Boolean checks ที่ใช้ใน guard clauses ควรตั้งชื่อโดยใช้คำนำหน้าเป็น `is_` สำหรับ expressions ที่ใช้ได้ สามารถดูที่ [Guard][Guard Expressions]
  <sup>[[link](#predicate-function-is-prefix)]</sup>

  ```elixir
  defguard is_cool(var) when var == "cool"
  defguard is_very_cool(var) when var == "very cool"
  ```

* <a name="private-functions-with-same-name-as-public"></a>
  ฟังก์ชันที่เป็น private ไม่ควรใช้ชื่อเดียวกับฟังก์ชันที่เป็น public นอกจากนี้ รูปแบบ `def name` และ `defp do_name` ก็ไม่แนะนำให้ใช้

  โดยทั่วไป ชื่อฟังก์ชันควรที่จะระบุจุดประสงค์ของฟังก์ชันได้อย่างชัดเจน
  <sup>[[link](#private-functions-with-same-name-as-public)]</sup>

  ```elixir
  def sum(list), do: sum_total(list, 0)

  # private functions
  defp sum_total([], total), do: total
  defp sum_total([head | tail], total), do: sum_total(tail, head + total)
  ```

<h3 id="comments">การใส่คอมเมนต์ (Comments)</h3>

* <a name="expressive-code"></a>
  เขียนโค้ดโดยที่ให้ผู้อ่านรู้ว่าโปรแกรมกำลังทำอะไรและพยายามสื่อความตั้งใจของโปรแกรมของคุณผ่าน control-flow, structure และ naming
  <sup>[[link](#expressive-code)]</sup>

* <a name="comment-grammar"></a>
  คอมเมนต์ที่ยาวกว่าหนึ่งคำจะเขียนด้วยตัวพิมพ์ใหญ่ ส่วนประโยคจะใช้เครื่องหมายวรรคตอน ใช้ [one space][Sentence Spacing] หลังจาก periods
  <sup>[[link](#comment-grammar)]</sup>

  ```elixir
  # ไม่แนะนำ
  # these lowercase comments are missing punctuation

  # แนะนำ
  # Capitalization example
  # Use punctuation for complete sentences.
  ```

* <a name="comment-line-length"></a>
  จำกัดไม่ให้เกิน 100 ตัวอักษร ในคอมเมนต์หนึ่งบรรทัด
  <sup>[[link](#comment-line-length)]</sup>

<h4 id="comment-annotations">การใส่คำอธิบายประกอบ (Comments Annotations)</h4>

* <a name="annotations"></a>
  คำอธิบายประกอบควรเขียนบนบรรทัดทันทีเหนือ code ที่เกี่ยวข้อง
  <sup>[[link](#annotations)]</sup>

* <a name="annotation-keyword"></a>
  คีย์เวิร์ดของคำอธิบายประกอบจะเขียนด้วยตัวพิมพ์ใหญ่ จากนั้นให้ตามด้วย colon และเว้น space จากนั้นเขียนค่อยคำอธิบาย
  <sup>[[link](#annotation-keyword)]</sup>

  ```elixir
  # TODO: Deprecate in v1.5.
  def some_function(arg), do: {:ok, arg}
  ```

* <a name="exceptions-to-annotations"></a>
  ในกรณีที่ปัญหาค่อนข้างจะชัดเจนมาก ให้ใส่คีย์เวิร์ดของคำอธิบายประกอบอย่างเดียว
  การใช้วิธีนี้ควรเป็นข้อยกเว้นแตไม่ใช่เป็นกฏ
  <sup>[[link](#exceptions-to-annotations)]</sup>

  ```elixir
  start_task()

  # FIXME
  Process.sleep(5000)
  ```

* <a name="todo-notes"></a>

  ใช้ `TODO` เพื่อบอกว่ามีฟีเจอร์หรือฟังก์ชันที่หายไปซึ่งควรเพิ่มเข้ามาในภายหลัง
  <sup>[[link](#todo-notes)]</sup>

* <a name="fixme-notes"></a>
  ใช้ `FIXME` เพื่อบอกว่าโค้ดที่มีปัญหาและต้องแก้ไข
  <sup>[[link](#fixme-notes)]</sup>

* <a name="optimize-notes"></a>
  ใช้ `OPTIMIZE` เพื่อบอกว่าโค้ดทำงานช้าหรือมีประสิทธิภาพที่ไม่เพียงพอซึ่งอาจทำให้เกิดปัญหาได้
  <sup>[[link](#optimize-notes)]</sup>

* <a name="hack-notes"></a>
  ใช้ `HACK` เพื่อบอกว่าโค้ดในส่วนมีความผิดปกติด้วยวิธีการเขียนโค้ดที่ดูน่าสงสัยและควรจะปรับปรุงใหม่
  <sup>[[link](#hack-notes)]</sup>

* <a name="review-notes"></a>
  ใช้ `REVIEW` เพื่อบอกว่าควรตรวจสอบเพื่อยืนยันว่ามันทำงานตามที่ตั้งใจไว้หรือไม่
  ตัวอย่างเช่น: `REVIEW: แน่ใจแล้วหรือไม่ ว่าผู้ใช้งานใช้ฟังค์ชั่นนี้ได้อย่างถูกต้อง?`
  <sup>[[link](#review-notes)]</sup>

* <a name="custom-keywords"></a>
  ใช้คีย์เวิร์ดของคำอธิบายประกอบอื่นๆ ตามความเหมาะสม แต่ต้องแน่ใจว่าได้มีการแจ้งไว้ใน `README` ของโปรเจกต์หรือเอกสารอื่นที่คล้ายคลึงกันแล้ว
  <sup>[[link](#custom-keywords)]</sup>

<h3 id="modules">โมดูล (Modules)</h3>

* <a name="one-module-per-file"></a>
  ใช้หนึ่ง module ต่อหนึ่งไฟล์ ยกเว้นในกรณีที่ module นั้นใช้ภายในโดย module อื่นเท่านั้น (เช่นการ testing)
  <sup>[[link](#one-module-per-file)]</sup>

* <a name="underscored-filenames"></a>
  ใช้ `snake_case` สำหรับชื่อไฟล์ และ `CamelCase` สำหรับชื่อของ module
  <sup>[[link](#underscored-filenames)]</sup>

  ```elixir
  # ชื่อไฟล์จะเป็น some_module.ex

  defmodule SomeModule do
  end
  ```

* <a name="module-name-nesting"></a>
  ในชื่อของ module ให้แสดงแต่ละเลเวลของ directory
  <sup>[[link](#module-name-nesting)]</sup>

  ```elixir
  # file is called parser/core/xml_parser.ex

  defmodule Parser.Core.XMLParser do
  end
  ```

* <a name="module-attribute-ordering"></a>
  ให้เรียง module attributes, directives, และ macros ตามลำดับนี้
  <sup>[[link](#module-attribute-ordering)]</sup>

  1. `@moduledoc`
  2. `@behaviour`
  3. `use`
  4. `import`
  5. `require`
  6. `alias`
  7. `@module_attribute`
  8. `defstruct`
  9. `@type`
  10. `@callback`
  11. `@macrocallback`
  12. `@optional_callbacks`
  13. `defmacro`, `defmodule`, `defguard`, `def`, etc.


  ให้เพิ่มบรรทัดว่างในแต่ละกลุ่ม และจัดเรียง (เช่น ชื่อ module) ตามตัวอักษร
  
  นี่คือตัวอย่างโดยรวมของวิธีการจัดเรียงสิ่งต่างๆ ใน modules ของคุณ:

  ```elixir
  defmodule MyModule do
    @moduledoc """
    An example module
    """

    @behaviour MyBehaviour

    use GenServer

    import Something
    import SomethingElse

    require Integer

    alias My.Long.Module.Name
    alias My.Other.Module.Example

    @module_attribute :foo
    @other_attribute 100

    defstruct [:name, params: []]

    @type params :: [{binary, binary}]

    @callback some_function(term) :: :ok | {:error, term}

    @macrocallback macro_name(term) :: Macro.t()

    @optional_callbacks macro_name: 1

    @doc false
    defmacro __using__(_opts), do: :no_op

    @doc """
    Determines when a term is `:ok`. Allowed in guards.
    """
    defguard is_ok(term) when term == :ok

    @impl true
    def init(state), do: {:ok, state}

    # จากนั้นค่อยใส่ฟังค์ชั่นอื่นๆ
  end
  ```

* <a name="module-pseudo-variable"></a>
  Use the `__MODULE__` pseudo variable when a module refers to itself. This
  avoids having to update any self-references when the module name changes.

  ใช้ `__MODULE__` เมื่อต้องการให้ module อ้างอิงถึงตัวของมันเอง การทำแบบนี้จะช่วยหลีกเลี่ยงเวลาที่เราเปลี่ยนชื่อ module จะได้ไม่ต้องอัปเดตทุกครั้ง
  <sup>[[link](#module-pseudo-variable)]</sup>

  ```elixir
  defmodule SomeProject.SomeModule do
    defstruct [:name]

    def name(%__MODULE__{name: name}), do: name
  end
  ```

* <a name="alias-self-referencing-modules"></a>
  สามารถใช้ alias สำหรับ `__MODULE__` เพื่อให้ชื่อมีความสวยงามมากขึ้น
  <sup>[[link](#alias-self-referencing-modules)]</sup>

  ```elixir
  defmodule SomeProject.SomeModule do
    alias __MODULE__, as: SomeModule

    defstruct [:name]

    def name(%SomeModule{name: name}), do: name
  end
  ```

* <a name="repetitive-module-names"></a>
  หลีกเลี่ยงการใช้ชื่อที่ซ้ำซ้อนของใน module และ namespaces สิ่งนี้ช่วยเพิ่มความชัดเจนโดยรวมและขจัด [ambiguous aliases][Conflicting Aliases].
  <sup>[[link](#repetitive-module-names)]</sup>

  ```elixir
  # ไม่แนะนำ
  defmodule Todo.Todo do
    ...
  end

  # แนะนำ
  defmodule Todo.Item do
    ...
  end
  ```
	
<h3 id="documentation">การเขียนเอกสารกำกับโปรแกรม (Documentation)</h3>

Elixir จะใช้ [Module Attributes] `@moduledoc` and `@doc`ในการเขียน document (ไม่ว่าจะอ่านจาก `h` (help function) ใน `iex`  หรือที่ถูกเขียนบน
[ExDoc]) 

* <a name="moduledocs"></a>
  ต้องใส่ `@moduledoc` ในบรรทัดที่ต่อจาก `defmodule` เสมอ
  <sup>[[link](#moduledocs)]</sup>

  ```elixir
  # ไม่แนะนำ

  defmodule AnotherModule do
    use SomeModule

    @moduledoc """
    About the module
    """
    ...
  end

  # แนะนำ

  defmodule AThirdModule do
    @moduledoc """
    About the module
    """

    use SomeModule
    ...
  end
  ```

* <a name="moduledoc-false"></a>
  ใส่ `@moduledoc false` เมื่อไม่ต้องการที่จะเขียน document ในโมดูลนั้นๆ
  <sup>[[link](#moduledoc-false)]</sup>

  ```elixir
  defmodule SomeModule do
    @moduledoc false
    ...
  end
  ```

* <a name="moduledoc-spacing"></a>
  เว้นหนึ่งบรรทัด เพื่อแยกโค้ดกับ `@moduledoc`
  <sup>[[link](#moduledoc-spacing)]</sup>

  ```elixir
  # ไม่แนะนำ
  defmodule SomeModule do
    @moduledoc """
    About the module
    """
    use AnotherModule
  end

  # แนะนำ
  defmodule SomeModule do
    @moduledoc """
    About the module
    """

    use AnotherModule
  end
  ```

* <a name="heredocs"></a>
  ใช้ heredocs ควบคู่กับ markdown เพื่อเขียน document.
  <sup>[[link](#heredocs)]</sup>

  ```elixir
  # ไม่แนะนำ
  defmodule SomeModule do
    @moduledoc "About the module"
  end

  defmodule SomeModule do
    @moduledoc """
    About the module

    Examples:
    iex> SomeModule.some_function
    :result
    """
  end

  # แนะนำ
  defmodule SomeModule do
    @moduledoc """
    About the module

    ## Examples

        iex> SomeModule.some_function
        :result
    """
  end
  ```

<h3 id="typespecs">การเขียนไทป์สเปค (Typespecs)</h3>

Typespecs เป็นรูปแบบที่เอาไว้สำหรับประกาศหรือระบุ types and specifications ทั้งสำหรับ documentation และเครื่องมือวิเคราะห์แบบสแตติกอย่าง Dialyzer

Custom types ควรถูกกำหนดไว้ในด้านบนของ module ร่วมกับ
directives อื่นๆ (ดูได้ที่ [Modules](#modules)).

* <a name="typedocs"></a>
  วาง `@typedoc` ไว้ใกล้ๆกันกับ `@type` และแยกกันโดยใช้การเว้นบรรทัด
  <sup>[[link](#typedocs)]</sup>

  ```elixir
  defmodule SomeModule do
    @moduledoc false

    @typedoc "The name"
    @type name :: atom

    @typedoc "The result"
    @type result :: {:ok, term} | {:error, term}

    ...
  end
  ```

* <a name="union-types"></a>
  หาก union type ยาวเกินกว่าจะอยู่ในบรรทัดเดียว ให้วางแต่ละส่วนของ type บนบรรทัดแยกต่างหาก โดยเยื้องออกไปหนึ่งระดับจากชื่อของ type
  <sup>[[link](#union-types)]</sup>

  ```elixir
  # ไม่แนะนำ
  @type long_union_type ::
          some_type | another_type | some_other_type | one_more_type | a_final_type

  # แนะนำ
  @type long_union_type ::
          some_type
          | another_type
          | some_other_type
          | one_more_type
          | a_final_type
  ```

* <a name="naming-main-types"></a>

  ตั้งชื่อ type หลักสำหรับ module ว่า `t` เช่น: type specification สำหรับ struct
  <sup>[[link](#naming-main-types)]</sup>

  ```elixir
  defstruct [:name, params: []]

  @type t :: %__MODULE__{
          name: String.t() | nil,
          params: Keyword.t()
        }
  ```

* <a name="spec-spacing"></a>
  วาง specifications ไว้ในบรรทัดด้านบนของฟังค์ชั่น หลังจาก @doc โดยที่ไม่แยกด้วยบรรทัดว่าง
  <sup>[[link](#spec-spacing)]</sup>

  ```elixir
  @doc """
  Some function description.
  """
  @spec some_function(term) :: result
  def some_function(some_data) do
    {:ok, some_data}
  end
  ```

<h3 id="structs">สตรัค (Structs)</h3>

* <a name="nil-struct-field-defaults"></a>
  ใช้ atoms แทนสำหรับฟิลด์ของ struct ที่มีค่าเริ่มต้นเป็น nil จากนั้นตามด้วยคำหลักอื่นๆ
  <sup>[[link](#nil-struct-field-defaults)]</sup>

  ```elixir
  # 
  defstruct name: nil, params: nil, active: true

  # แนะนำ
  defstruct [:name, :params, active: true]
  ```

* <a name="struct-def-brackets"></a>
  ไม่ต้องใส่วงเล็บเมื่อ argument ของ `defstruct` เป็น keyword list
  <sup>[[link](#struct-def-brackets)]</sup>

  ```elixir
  # ไม่แนะนำ
  defstruct [params: [], active: true]

  # แนะนำ
  defstruct params: [], active: true

  # จำเป็นต้องใส่วงเล็บ ถ้าหากมี atom อยู่ใน list
  defstruct [:name, params: [], active: true]
  ```

* <a name="multiline-structs"></a>
  เมื่อต้องสร้าง struct ที่มีหลายบรรทัด ควรใส่ element ไว้เพียงตัวเดียวต่อหนึ่งบรรทัด และจัดเรียงให้อยู่ในแนวเดียวกัน
  <sup>[[link](#multiline-structs)]</sup>

  ```elixir
  defstruct foo: "test",
            bar: true,
            baz: false,
            qux: false,
            quux: 1
  ```

  ถ้าหากต้องใส่วงเล็บควรจัดรูปแบบตามนี้

  ```elixir
  defstruct [
    :name,
    params: [],
    active: true
  ]
  ```


<h3 id="exceptions">การจัดการกับข้อผิดพลาด (Exceptions)</h3>

* <a name="exception-names"></a>
  เวลาตั้งชื่อ exception ให้ต่อท้ายด้วย `Error`
  <sup>[[link](#exception-names)]</sup>

  ```elixir
  # ไม่แนะนำ
  defmodule BadHTTPCode do
    defexception [:message]
  end

  defmodule BadHTTPCodeException do
    defexception [:message]
  end

  # แนะนำ
  defmodule BadHTTPCodeError do
    defexception [:message]
  end
  ```

* <a name="lowercase-error-messages"></a>

  ให้ใช้ตัวอักษรเล็กสำหรับข้อความ error โดยที่ไม่ต้องใส่เครื่องหมายวรรคตอน
  <sup>[[link](#lowercase-error-messages)]</sup>

  ```elixir
  # ไม่แนะนำ
  raise ArgumentError, "This is not valid."

  # แนะนำ
  raise ArgumentError, "this is not valid"
  ```

<h3 id="collections">คอลเลกชัน (Collections)</h3>

* <a name="keyword-list-syntax"></a>
  ต้องใช้ syntax พิเศษสำหรับ keyword lists เสมอ
  <sup>[[link](#keyword-list-syntax)]</sup>

  ```elixir
  # ไม่แนะนำ
  some_value = [{:a, "baz"}, {:b, "qux"}]

  # แนะนำ
  some_value = [a: "baz", b: "qux"]
  ```

* <a name="map-key-atom"></a>
  เมื่อทุก key ใน map เป็น atom ทั้งหมด ให้ใช้ syntax เป็นแบบ shorthand key-value
  <sup>[[link](#map-key-atom)]</sup>

  ```elixir
  # ไม่แนะนำ
  %{:a => 1, :b => 2, :c => 0}

  # แนะนำ
  %{a: 1, b: 2, c: 3}
  ```

* <a name="map-key-arrow"></a>
  ถ้าหากมี key ใดที่ไม่ใช่ atom เพียง key เดียวใน map ให้ใช้ syntax แบบ verbose key-value 
  <sup>[[link](#map-key-arrow)]</sup>

  ```elixir
  # ไม่แนะนำ
  %{"c" => 0, a: 1, b: 2}

  # แนะนำ
  %{:a => 1, :b => 2, "c" => 0}
  ```

<h3 id="strings">สตริง (Strings)</h3>

* <a name="strings-matching-with-concatenator"></a>
  เมื่อต้องการที่จะเทียบ string ให้ใช้ string concatenator มากกว่า binary patterns
  <sup>[[link](#strings-matching-with-concatenator)]</sup>

  ```elixir
  # ไม่แนะนำ
  <<"my"::utf8, _rest::bytes>> = "my string"

  # แนะนำ
  "my" <> _rest = "my string"
  ```

<h3 id="strings">นิพจน์ปรกติ (Regular Expressions)</h3>
 
_ยังไม่มีคู่มือสำหรับนิพจน์ปรกติ (Regular Expressions) ในตอนนี้_

### Metaprogramming

<h3 id="metaprogramming">เมต้าโปรแกรมมิ่ง (Metaprogramming)</h3>

* <a name="avoid-metaprogramming"></a>
  หลีกเลี่ยงการใช้ metaprogramming ที่ไม่จำเป็น
  <sup>[[link](#avoid-metaprogramming)]</sup>

### Testing
<h3 id="testing">การทดสอบโปรแกรม (testing)</h3>

* <a name="testing-assert-order"></a>

  เมื่อเขียน [ExUnit] assertions, ให้วาง expression ที่กำลังทดสอบไว้ทางซ้ายของ operator และวาง expected result ไว้ทางขวา ยกเว้นในกรณีที่ assertion เป็น pattern match
  <sup>[[link](#testing-assert-order)]</sup>

  ```elixir
  # แนะนำ
  assert actual_function(1) == true

  # ไม่แนะนำ
  assert true == actual_function(1)

  # pattern match ต้องวางทางด้านซ้ายเสมอ
  assert {:ok, expected} = actual_function(3)
  ```

<h2 id="resources">แหล่งที่มา (Resources)</h2>

<h3 id="alternative-style-guides">คู่มืออื่นๆ (Alternative Style Guides)</h3>

* [Aleksei Magusev's Elixir Style Guide](https://github.com/lexmag/elixir-style-guide#readme)
  — คู่มือ Elixir ที่มีความเฉพาะเจาะจง ซึ่งได้รับการพัฒนาตามแบบแผนของการเขียนโค้ดที่ใช้ใน Elixir core libraries
  พัฒนาโดย [Aleksei Magusev](https://github.com/lexmag) และ
  [Andrea Leopardi](https://github.com/whatyouhide), สมาชิกหลักของทีม Elixir

  แม้ว่าโปรเจกต์ Elixir จะไม่ยึดติดกับคู่มือรูปแบบการเขียนโค้ดใดๆ แต่นี่คือคู่มือที่ใกล้เคียงที่สุดกับแบบแผนที่ใช้ในโปรเจกต์ต่างๆ

* [Credo's Elixir Style Guide](https://github.com/rrrene/elixir-style-guide#readme)
  — คู่มือสำหรับภาษา Elixir  เขียนโดย
  [Credo](http://credo-ci.org)

<h3 id="tools">เครื่องมือ (Tools)</h3>

สำหรับ libraries และ tools ที่สามารถช่วยในการวิเคราะห์โค้ดและ style linting สามารถดูได้ที่ [Awesome Elixir][Code Analysis]

<h2 id="getting-involved">เข้ามามีส่วนร่วมกับเรา</h2>

<h3 id="contributing">การสนับสนุน (Contributing)</h3>

เราหวังว่าสิ่งนี้จะกลายเป็นศูนย์กลางสำหรับ community ที่พูดคุยเกี่ยวกับ best practice ต่างๆ ใน Elixir อย่าลังเลที่จะเปิด tickets หรือส่ง pull requests เพื่อให้ข้อเสนอแนะ ขอบคุณล่วงหน้าสำหรับความช่วยเหลือของคุณ!

ข้อมูลเพิ่มเติมสามารถดูได้ใน [contributing guidelines][Contributing] 

<h3 id="spread-the-word">เผยแพร่ข่าวสาร (Spread the Word)</h3>

Community นี้จะไม่มีความหมายหากไม่ได้รับการสนับสนุนจากเพื่อนๆใน community ด้วยการ tweet, ให้ดาว [star][Stargazers] และแจ้งให้ Elixir developer ทุกคนทราบเกี่ยวกับ [คู่มือนี้][Elixir Style Guide] เพื่อให้พวกเขาสามารถมีส่วนร่วมได้

<h2 id="copying">การก๊อปปี้ (Copying)</h2>

<h3 id="license">ลิขสิทธิ์ (License)</h3>

![Creative Commons License](http://i.creativecommons.org/l/by/3.0/88x31.png)
Repo นี้ได้รับการอนุญาตภายใต้
[Creative Commons Attribution 3.0 Unported License][License]

<h3 id="attribution">การยกเครดิต (Attribution)</h3>

โครงสร้าง โค้ดตัวอย่าง และหลายประเด็นที่กล่าวในคู่มือนี้ นี้ได้ยืมมาจาก [Ruby community style guide] มีหลายอย่างที่สามารถใช้ใน Elixir ได้ และช่วยให้พวกเราสามารถสร้างเอกสารบางส่วนได้เร็วขึ้น

[list ของผู้คนที่มีส่วนร่วมในนี้][Contributors]

<!-- Links -->
[Chinese Simplified]: https://github.com/geekerzp/elixir_style_guide/blob/master/README-zhCN.md
[Chinese Traditional]: https://github.com/elixirtw/elixir_style_guide/blob/master/README_zhTW.md
[Code Analysis]: https://github.com/h4cc/awesome-elixir#code-analysis
[Code Of Conduct]: https://github.com/elixir-lang/elixir/blob/master/CODE_OF_CONDUCT.md
[Code Formatter]: https://hexdocs.pm/elixir/Code.html#format_string!/2
[Conflicting Aliases]: https://elixirforum.com/t/using-aliases-for-fubar-fubar-named-module/1723
[Contributing]: https://github.com/christopheradams/elixir_style_guide/blob/master/CONTRIBUTING.md
[Contributors]: https://github.com/christopheradams/elixir_style_guide/graphs/contributors
[Elixir Style Guide]: https://github.com/christopheradams/elixir_style_guide
[Elixir]: http://elixir-lang.org
[ExDoc]: https://github.com/elixir-lang/ex_doc
[ExUnit]: https://hexdocs.pm/ex_unit/ExUnit.html
[French]: https://github.com/ronanboiteau/elixir_style_guide/blob/master/README_frFR.md
[Guard Expressions]: https://hexdocs.pm/elixir/patterns-and-guards.html#list-of-allowed-functions-and-operators
[Hex]: https://hex.pm/packages
[Japanese]: https://github.com/kenichirow/elixir_style_guide/blob/master/README-jaJP.md
[Korean]: https://github.com/marocchino/elixir_style_guide/blob/new-korean/README-koKR.md
[License]: http://creativecommons.org/licenses/by/3.0/deed.en_US
[Mix format]: https://hexdocs.pm/mix/Mix.Tasks.Format.html
[Module Attributes]: http://elixir-lang.org/getting-started/module-attributes.html#as-annotations
[Naming Conventions]: https://hexdocs.pm/elixir/naming-conventions.html
[Portuguese]: https://github.com/gusaiani/elixir_style_guide/blob/master/README_ptBR.md
[Ruby community style guide]: https://github.com/bbatsov/ruby-style-guide
[Russian]: https://github.com/sofialapteva/elixir_style_guide/blob/russian/README_ru.md
[Sentence Spacing]: http://en.wikipedia.org/wiki/Sentence_spacing
[Spanish]: https://github.com/iver/elixir_style_guide/blob/spanish/i18n/README_es.md
[Thai]: https://github.com/tamectosphere/elixir_style_guide/blob/feat/thai-translation/README_th.md
[Stargazers]: https://github.com/christopheradams/elixir_style_guide/stargazers
