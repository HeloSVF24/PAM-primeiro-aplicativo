package com.example.businesscard

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.activity.enableEdgeToEdge
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.layout.ContentScale
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.businesscard.ui.theme.BusinessCardTheme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            BusinessCardTheme {
                BackgroundImage()
            }
        }
    }
}

@Composable
fun BackgroundImage() {
    Box(modifier = Modifier.fillMaxSize()) {
        val image = painterResource(id = R.drawable.ceu)

        Image(
            painter = image,
            contentDescription = null,
            modifier = Modifier.fillMaxSize(),
            contentScale = ContentScale.Crop
        )

        BusinessCardContent()
    }
}

@Composable
fun BusinessCardContent() {
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
    Column(horizontalAlignment = Alignment.CenterHorizontally) {
        val image = painterResource(id = R.drawable.)

        Image(
            painter = image,
            contentDescription = "Perfil",
            modifier = Modifier
                .size(140.dp)
                .clip(CircleShape),
            contentScale = ContentScale.Crop
        )
        Spacer(modifier = Modifier.size(16.dp))

        Text(
            text = "Heloisa Silva Verly Fonseca",
            fontSize = 28.sp,
            textAlign = TextAlign.Center,
            modifier = Modifier.padding(horizontal = 24.dp),
            color = Color.Black
        )

        Text(
            text = "Estudante da Etec da Zona Leste",
            fontSize = 20.sp,
            color = Color.DarkGray
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
        ContactRow("👤", "Quem sou eu? Uma garota que sonha em ser veterinária de animais silvestres.")
        Spacer(modifier = Modifier.size(8.dp))
        ContactRow("📞", "11 95721-4069")
        Spacer(modifier = Modifier.size(8.dp))
        ContactRow("✉️", "heloisasvfonseca@gmail.com")
    }
}

@Composable
fun ContactRow(icon: String, text: String) {
    Row(
        verticalAlignment = Alignment.CenterVertically,
        modifier = Modifier.padding(8.dp)
    ) {
        Text(text = icon, fontSize = 20.sp)
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
        BackgroundImage()
    }
}
