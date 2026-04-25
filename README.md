[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/_ZP6rv38)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23677227&assignment_repo_type=AssignmentRepo)
# Lập trình trên thiết bị di động
## Dự án 1: Danh thiếp (Bussiness card)
- Commit code tại repo này

- 
  package com.example.baitap17
  
  import android.os.Bundle
  import androidx.activity.ComponentActivity
  import androidx.activity.compose.setContent
  import androidx.compose.foundation.Image
  import androidx.compose.foundation.background
  import androidx.compose.foundation.layout.Arrangement
  import androidx.compose.foundation.layout.Column
  import androidx.compose.foundation.layout.Row
  import androidx.compose.foundation.layout.fillMaxSize
  import androidx.compose.foundation.layout.fillMaxWidth
  import androidx.compose.foundation.layout.padding
  import androidx.compose.foundation.layout.size
  import androidx.compose.material3.Icon
  import androidx.compose.material3.MaterialTheme
  import androidx.compose.material3.Surface
  import androidx.compose.material3.Text
  import androidx.compose.runtime.Composable
  import androidx.compose.ui.Alignment
  import androidx.compose.ui.Modifier
  import androidx.compose.ui.graphics.Color
  import androidx.compose.ui.res.painterResource
  import androidx.compose.ui.text.font.FontWeight
  import androidx.compose.ui.tooling.preview.Preview
  import androidx.compose.ui.unit.dp
  import androidx.compose.ui.unit.sp
  import com.example.baitap17.ui.theme.Baitap17Theme
  
  
  class MainActivity : ComponentActivity() {
      override fun onCreate(savedInstanceState: Bundle?) {
          super.onCreate(savedInstanceState)
          setContent {
              Baitap17Theme {
                  Surface(
                      modifier = Modifier.fillMaxSize(),
                      color = MaterialTheme.colorScheme.background
                  ) {
                      DanhThiep()
                  }
              }
          }
      }
  }
  
  @Composable
  fun DanhThiep() {
      Column(
          modifier = Modifier
              .fillMaxSize()
              .background(Color(0xFFD2E8D4)),
          horizontalAlignment = Alignment.CenterHorizontally
      ) {
          Column(
              modifier = Modifier.weight(1f),
              horizontalAlignment = Alignment.CenterHorizontally,
              verticalArrangement = Arrangement.Center
          ) {
              Image(
                  painter = painterResource(id = R.drawable.android_logo),
                  contentDescription = "Android Logo",
                  modifier = Modifier
                      .size(100.dp)
                      .background(Color(0xFF073042))
                      .padding(8.dp)
              )
  
              Text(
                  text = "Nguyễn Xuân Tùng",
                  color = Color(0xFF000000),
                  fontSize = 30.sp,
                  modifier = Modifier.padding(top = 16.dp, bottom = 8.dp)
              )
  
              Text(
                  text = "Sinh viên lớp CNTT CT1C",
                  color = Color(0xFF2E7D32),
                  fontWeight = FontWeight.Bold,
                  fontSize = 24.sp
              )
          }
  
          Column(
              modifier = Modifier
                  .fillMaxWidth()
                  .padding(start = 80.dp, bottom = 80.dp),
              verticalArrangement = Arrangement.spacedBy(12.dp),
              horizontalAlignment = Alignment.Start 
          ){
              DongLienHe(iconId = R.drawable.sodienthoai, text = "+84 89 626 256")
              DongLienHe(iconId = R.drawable.chiase, text = "@Xuantung05")
              DongLienHe(iconId = R.drawable.email, text = "xuantung05@gmail.com")
          }
      }
  }
  
  @Composable
  fun DongLienHe(iconId: Int, text: String) {
      Row(
          modifier = Modifier.fillMaxWidth(),
          verticalAlignment = Alignment.CenterVertically,
          horizontalArrangement = Arrangement.Start
      ){
          Icon(
              painter = painterResource(id = iconId),
              contentDescription = null,
              tint = Color(0xFF2E7D32),
              modifier = Modifier.size(24.dp)
          )
  
          Text(
              text = text,
              color = Color(0xFF000000),
              fontSize = 18.sp,
              modifier = Modifier.padding(start = 12.dp) 
          )
      }
  }
  
  @Preview(showBackground = true)
  @Composable
  fun DanhThiepPreview() {
      Baitap17Theme() {
          DanhThiep()
      }
  }
      
