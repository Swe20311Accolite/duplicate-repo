pipeline {
  agent any
  stages {
    stage('checkout-repo') {
      parallel {
        stage('checkout-repo1') {
          agent any
          steps {
            sh 'mkdir repo'
            dir(path: 'repo') {
              git(url: 'https://github.com/Swe20311Accolite/cluster-repo.git', branch: 'main')
            }

          }
        }

        stage('checkout-repo') {
          steps {
            sh 'mkdir repo1'
            dir(path: 'repo1') {
              git(url: 'https://github.com/Swe20311Accolite/cluster-repo.git', branch: 'dev')
            }

          }
        }

      }
    }

    stage('testing') {
      steps {
        kubeconfig(serverUrl: 'https://192.168.49.2:8443', caCertificate: 'LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSURCakNDQWU2Z0F3SUJBZ0lCQVRBTkJna3Foa2lHOXcwQkFRc0ZBREFWTVJNd0VRWURWUVFERXdwdGFXNXAKYTNWaVpVTkJNQjRYRFRJeE1EVXhNekUzTURrd01Wb1hEVE14TURVeE1qRTNNRGt3TVZvd0ZURVRNQkVHQTFVRQpBeE1LYldsdWFXdDFZbVZEUVRDQ0FTSXdEUVlKS29aSWh2Y05BUUVCQlFBRGdnRVBBRENDQVFvQ2dnRUJBUEhECjZZNVVoOFRuR0J0dnUyWWw5ZzJSQUdBRHZqaS9FdkVhNzd0VUY1M3ZmcEE2aS9Rb0NzWjZibUhSZ2ZDdUxYV2IKNEFTenptTGNSUE85ZmRCNTRjdUpDSVlqZWtGczEwNjBjUmFKK3crVmM0dWo0Rys0SGVaVzhJUk51eTErSXliVgpha1p3UDUycmlrRm9DRk5GZ1dvZ0dYU2d3Z255ejBMWDllNUh3R0R2ZHduWURaZjRjUnR0ZjdFU0o2akZ0Y3NDClEwMW0yQWlZQllJSklVQWl0akZaL2ZTVDhlZWNEN0RQaERYOXpMUVIwYTVtWUZsZWIrc3JIVnZXaHRRZTc2dzEKelZDelQrN010SXU3M2o5Z1E1M3FxZkxTckhRcHN0MVF5NjVuY21BNGE1RGNGTS9McFVWWHZaZ1ROcm00Ymw3QgpENzZ6K1Jya0EvTTlxU0JtWHFzQ0F3RUFBYU5oTUY4d0RnWURWUjBQQVFIL0JBUURBZ0trTUIwR0ExVWRKUVFXCk1CUUdDQ3NHQVFVRkJ3TUNCZ2dyQmdFRkJRY0RBVEFQQmdOVkhSTUJBZjhFQlRBREFRSC9NQjBHQTFVZERnUVcKQkJTQkpoZ2QyTEwyZkM0YVo5aDBPcXBkZ2p6b3BUQU5CZ2txaGtpRzl3MEJBUXNGQUFPQ0FRRUFTcG9vS2FCbwo2QUFKTkpzVnd3Uk9iWHhuTTZlT3R1S0JrWjlDSHB5RDFTbE1GQktuMHl5OSswK0tWMW9tUlY2bjVCV2VDTnEzCmZ4WUhWVXpzSVVUL1R0NlUrTHF6Q1NFQklRN2U2YU14ZlQ2Z0RMR3JWQXlPcEU4NWw3WVo3dEtuYTJCQ0lVN04KRmFTL2wrbUI0blhCVWxXT043K0h1T2hwdnhYSGlkeHhhendXQVZhWCtWMlF0RUJ0Y2o1NlEzSDZRSVp2TjZSMwpNRk1uY3I3cHZBQVJOaUZzemxuOW9GQ3ViNlJFQWhxR3RQc0YzdGp0OXFDRnM0MStBZUJTRDhSY0wvWmc2NnZkCnpHSlRibUl3bUVuVlBaV3JYbndaOW5KeC9GR0FaKzZkWXFxbnc1UVhzRmVXWnJXZ3NPd2VXS29qd0s1Nk1xS3UKMks3K1k4Qm5HUTI5RWc9PQotLS0tLUVORCBDRVJUSUZJQ0FURS0tLS0tCg==', credentialsId: 'b9527f91-e186-42ce-84af-0e3d530ae39f') {
          sh 'kubectl get all'
        }

      }
    }

  }
}