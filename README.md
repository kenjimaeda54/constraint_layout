# Reforcando conceito do constraint layou


## Motivacao
Recordar o uso do contranst layout para criar aplicativos



## Feature 
- Constraint layout trabalho com conceito de constraintTop_toTopOf,constraintTop_toBottomOf.
- Consegue alinhar conforme com o pai ou outros filhos segundo conceito de constraintTop, constraintBottom
- Para criar o layout e obrigatório pelo menos dois lados referenciados, ou seja, um constraint vertical e outro horizontal
- Existe um recurso conhecido como bias, ele possui horizontal e vertical.
- Bias diminui a forca das correntes
- Também e possível construir layouts usando recurso de angulo, para funcionar precisa ser em relação ao um filho
- Outro recurso que semelha muito ao flex box e o uso de chain
- Existe spreat_inside,packed e spread
- Spreat_inside ele espalha os itens conforme as bordas assim as distâncias entre filhos ficam maiores
- Spreat aproxima os filhos assim a distancia fica menor
- O padrão e o packed, ele não afeta os filhos
- Para usar o recurso de chain os filhos precisam estar interligados


``` kotlin


<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
    <!--   conceito chain e bem parecido com flexbox  packed e o padrao nao altera comportamento, spread fica seprado e distanciam da borda, spread_inside espalham para perto das bordas -->
    <Button
        android:id="@+id/buttonA"
        android:layout_marginTop="20dp"
        android:layout_marginLeft="20dp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button A"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintLeft_toRightOf="@id/buttonB"
        app:layout_constraintRight_toLeftOf="@id/buttonB"
        app:layout_constraintHorizontal_chainStyle="spread_inside"
        />
    <Button
        android:id="@+id/buttonB"
        android:layout_marginTop="20dp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button B"
        app:layout_constraintLeft_toRightOf="@+id/buttonA"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintRight_toLeftOf= "@id/buttonF"
        />
    <Button
        android:id="@+id/buttonF"
        android:layout_marginTop="20dp"
        android:layout_marginRight="20dp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button F"
        app:layout_constraintLeft_toRightOf="@+id/buttonB"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        />
    <Button
        android:id="@+id/buttonC"
        android:layout_marginTop="20dp"
        android:layout_marginLeft="20dp"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Button C"
        app:layout_constraintTop_toBottomOf="@id/buttonB"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        android:layout_marginRight="20dp"
        />
    <!--        cuidado com o width se estiver 0 ou match vai tentar ocupar tudo disponivel-->
    <!--        bias faz com que a mola perca a forca    -->
  <Button
      android:id="@+id/buttonD"
      android:layout_marginTop="20dp"
      android:layout_marginLeft="20dp"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:text="Button D"
      app:layout_constraintBottom_toBottomOf="parent"
      app:layout_constraintTop_toBottomOf="@id/buttonC"
      app:layout_constraintLeft_toLeftOf="parent"
      app:layout_constraintRight_toRightOf="parent"
      app:layout_constraintHorizontal_bias="0.5"
      app:layout_constraintVertical_bias="0.8"
      />
    <!--        cuidado com o width se estiver 0 ou match vai tentar ocupar tudo disponivel-->
    <!--        bias faz com que a mola propriedade angulo    -->
    <Button
        android:id="@+id/buttonE"
        android:layout_marginTop="20dp"
        android:layout_marginLeft="20dp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button E"
        app:layout_constraintLeft_toLeftOf="@id/buttonD"
        app:layout_constraintTop_toTopOf="@id/buttonD"
        app:layout_constraintCircle="@id/buttonD"
        app:layout_constraintCircleRadius="130dp"
        app:layout_constraintCircleAngle="75"
        />


</androidx.constraintlayout.widget.ConstraintLayout>





```





