// FaceGuard AI - Android App (Kotlin with AWS Backend Integration)

// This is the main layout for the Android project using Jetpack Compose // and Amazon Rekognition integration for facial recognition security.

import android.os.Bundle import androidx.activity.ComponentActivity import androidx.activity.compose.setContent import androidx.compose.foundation.layout.* import androidx.compose.material3.* import androidx.compose.runtime.* import androidx.compose.ui.Alignment import androidx.compose.ui.Modifier import androidx.compose.ui.unit.dp import androidx.compose.ui.unit.sp import com.amazonaws.mobile.client.AWSMobileClient import com.amazonaws.mobile.config.AWSConfiguration import com.amazonaws.services.rekognition.AmazonRekognitionClient

class MainActivity : ComponentActivity() { override fun onCreate(savedInstanceState: Bundle?) { super.onCreate(savedInstanceState)

// Initialize AWS
    AWSMobileClient.getInstance()
        .initialize(applicationContext, AWSConfiguration(applicationContext)) {
            println("AWSMobileClient is initialized")
        }
        .execute()

    setContent {
        FaceGuardApp()
    }
}

}

@Composable fun FaceGuardApp() { Surface(color = MaterialTheme.colorScheme.background) { Column( modifier = Modifier .fillMaxSize() .padding(20.dp), horizontalAlignment = Alignment.CenterHorizontally, verticalArrangement = Arrangement.Center ) { Text("Welcome to FaceGuard AI", fontSize = 24.sp) Spacer(modifier = Modifier.height(16.dp)) Button(onClick = { /* Open Camera, Trigger Face Recognition */ }) { Text("Scan Face") } Spacer(mod

# Trial-app
Security 
