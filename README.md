<div align="right">
  <img src="https://img.shields.io/badge/Date-2026--03--10-blue?style=for-the-badge" alt="Date" />
  <img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge" alt="Status" />
  <img src="https://img.shields.io/badge/Tier-Master-gold?style=for-the-badge" alt="Tier" />
</div>

# Thirsty-lang Mobile App 💧📱

Cross-platform mobile application framework for iOS and Android.

## Features

- Cross-platform (iOS/Android)
- Native UI components  
- Geolocation & maps
- Camera & media
- Push notifications
- Local storage
- Networking

## Quick Start

```thirsty
import { App, Screen, Button, Text } from "mobile"

glass HomeScreen extends Screen {
  glass render() {
    return `
      <View>
        <Text style="title">Welcome!</Text>
        <Button onPress=${handlePress}>Get Started</Button>
      </View>
    `
  }
  
  glass handlePress() {
    navigate("Profile")
  }
}

drink app = App(reservoir {
  screens: reservoir {
    Home: HomeScreen,
    Profile: ProfileScreen
  }
})

app.start()
```

## Native Components

```thirsty
// Camera
glass CameraScreen {
  glass async takePicture() {
    drink photo = await Camera.capture()
    await uploadPhoto(photo)
  }
}

// Geolocation
glass MapScreen {
  glass async getLocation() {
    drink location = await Geolocation.getCurrentPosition()
    pour `Lat: ${location.latitude}, Lon: ${location.longitude}`
  }
}

// Push Notifications
glass NotificationService {
  glass async requestPermission() {
    drink granted = await PushNotifications.requestPermission()
    return granted
  }
  
  glass subscribe(topic) {
    PushNotifications.subscribe(topic)
  }
}
```

## License

MIT
