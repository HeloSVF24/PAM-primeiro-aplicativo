# PAM-primeiro-aplicativo

package com.example.businesscard

import android.R
import android.graphics.drawable.Icon
import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.activity.enableEdgeToEdge
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.padding
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.tooling.preview.Preview
import com.example.businesscard.ui.theme.BusinessCardTheme
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.layout.ContentScale
import androidx.compose.ui.modifier.modifierLocalOf
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            BusinessCardTheme {
                Scaffold(modifier = Modifier.fillMaxSize()) { innerPadding ->
                   BusinessCard()
                    BackgroudImage()
                }
            }
        }
    }
}

@Composable
fun BusinessCard(modifier: Modifier = Modifier) {
    Column(modifier = Modifier.fillMaxSize(),
        verticalArrangement = Arrangement.SpaceBetween,
        horizontalAlignment = Alignment.CenterHorizontally
        ){
        Spacer(modifier = Modifier.weight(1f))
        ProfileSection()
        Spacer(modifier = Modifier.weight(1f))
        ContactSection()
    }
}

@Composable
fun BackgroudImage() {
    val image = painterResource(R.drawable.)
    Image(
        painter = image,
        contentDescription = null,
        modifier = Modifier.fillMaxSize(),
        contentScale = ContentScale.Crop
    )

    Column(
        modifier = Modifier.fillMaxSize(),
        verticalArrangement = Arrangement.SpaceBetween,
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        Spacer(modifier = Modifier.weight(1f))
        ProfileSection()
        Spacer(modifier = Modifier.weight(1f))
        ContactSection()
    }
}

@Composable
fun ProfileSection() {
    Column(horizontalAlignment = Alignment.CenterHorizontally,
    ) {
        val image = painterResource()
        Image(
            paiter = image,
            contentDescription = "Perfil",
            modifier = Modifier
                .size(140.dp)
                .clip(CircleShape)
        )
        Spacer(modifier = Modifier.size(16.dp))

        Text(
            text = "Heloisa Silva Verly Fonseca",
            fontSize = 32.sp,
            textAlign = TextAlign.Center,
            modifier = Modifier.padding(horizontal = 24.dp),
            color = Color.Black
        )

        Text(
            text = "Estudante da Etec da Zona Leste",
            fontSize = 32.sp,
            color = Color.Black
        )
    }
}

@Composable
fun ContactSection() {
    Column(
        modifier = Modifier
            .padding(bottom = 48.dp)
            .padding(horizontal = 16.dp)
    ) {
        ContactRow("Quem sou eu? Uma garota que sonha em se tornar uma vaterinária de animais silvestres.")
        Spacer(modifier = Modifier.size(8.dp))

        ContactRow("11 95721-4069")
        Spacer(modifier = Modifier.size(8.dp))

        ContactRow("e-mail: heloisasvfonseca@gmail.com")
    }
}

@Composable
fun ContactRow(icon: String, text: String) {
    Row(verticalAlignment = Alignment.CenterVertically,
        modifier = Modifier.padding(8.dp)
    ) {
        Text(
            text = icon,
            fontSize = 20.sp,
            modifier = Modifier.size(24.dp)
        )

        Text(
            text = text,
            fontSize = 16.sp,
            modifier = Modifier.padding(start = 16.dp),
            color = Color.Black
        )
    }
}

@Preview(showBackground = true)
@Composable
fun GreetingPreview() {
    BusinessCardTheme {
        Scaffold(modifier = Modifier.fillMaxSize()) { innerPadding ->
            BusinessCard()
            BackgroudImage()
}
