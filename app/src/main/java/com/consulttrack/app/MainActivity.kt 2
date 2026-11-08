package com.consulttrack.app

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Modifier
import androidx.compose.ui.unit.dp
import androidx.compose.ui.text.font.FontWeight

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            ConsultTrackApp()
        }
    }
}

@Composable
fun ConsultTrackApp() {
    MaterialTheme {
        var selected by remember { mutableStateOf("Toutes") }

        Scaffold(
            topBar = {
                TopAppBar(
                    title = {
                        Text(
                            "ConsultTrack",
                            fontWeight = FontWeight.Bold
                        )
                    }
                )
            }
        ) { padding ->
            LazyColumn(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(padding)
                    .padding(16.dp),
                verticalArrangement = Arrangement.spacedBy(14.dp)
            ) {
                item {
                    Text(
                        "Tableau de bord",
                        style = MaterialTheme.typography.headlineSmall
                    )
                }

                item {
                    Row(horizontalArrangement = Arrangement.spacedBy(8.dp)) {
                        StatCard("Total", "0")
                        StatCard("En cours", "0")
                    }
                }

                item {
                    Row(horizontalArrangement = Arrangement.spacedBy(8.dp)) {
                        StatCard("Déposés", "0")
                        StatCard("Gagnés", "0")
                    }
                }

                item {
                    Text(
                        "Mes consultations",
                        style = MaterialTheme.typography.titleLarge
                    )
                }

                item {
                    Row(horizontalArrangement = Arrangement.spacedBy(6.dp)) {
                        listOf("Toutes", "En cours", "Terminées").forEach {
                            FilterChip(
                                selected = selected == it,
                                onClick = { selected = it },
                                label = { Text(it) }
                            )
                        }
                    }
                }

                item {
                    Card(modifier = Modifier.fillMaxWidth()) {
                        Column(Modifier.padding(18.dp)) {
                            Text("Aucune consultation")
                            Text("Ajoutez votre première consultation.")
                        }
                    }
                }

                item {
                    Button(
                        onClick = { },
                        modifier = Modifier.fillMaxWidth()
                    ) {
                        Text("+ Nouvelle consultation")
                    }
                }
            }
        }
    }
}

@Composable
fun StatCard(title: String, value: String) {
    Card(modifier = Modifier.weight(1f)) {
        Column(Modifier.padding(16.dp)) {
            Text(title)
            Text(
                value,
                style = MaterialTheme.typography.headlineMedium,
                fontWeight = FontWeight.Bold
            )
        }
    }
}
