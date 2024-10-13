<template>
  <!-- <div class="home">
    <img alt="Vue logo" src="../assets/mrk.svg">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div> -->
  
  <section>
    <div class="container-fluid">
      <div class="row">
        <!-- Sidebar -->
        <nav id="sidebar" class="col-md-3 col-lg-2 d-md-block bg-light sidebar">
          <img alt="" src="../assets/mrk.svg">
          <ul class="nav flex-column text-start">
            <li class="nav-item">
              <a class="nav-link active text-light" style="background-color: blue; border-radius: 15px;">
                  <img alt="" src="../assets/ss.svg"> Dashboard
              </a>
            </li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/ord.svg" />Orders</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/passen.svg" />Passengers</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/capt.svg" />Captains</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/cate.svg" />Categories</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/sett.svg" />Settlement</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/contac.svg" />Contact</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/revi.svg" />Reviews</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/perm.svg" />Permissions</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/tran.svg" />Translation</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/educ.svg" />Education Video</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/setin.svg" />Settings</a></li>
            <li class="nav-item"><a class="nav-link text-black"><img src="../assets/content.svg" />Content</a></li>
          </ul>
        </nav>

        <!-- Main Content Column -->
        <div class="col-md-9 col-lg-10 d-flex flex-column">
          <div class="search-bar d-flex align-items-center justify-content-between p-2">
            <!-- Search Box -->
            <div class="search-box d-flex align-items-center border-dashed p-2 me-3">
              <i class="bi bi-search me-2"></i>
             
            </div>

            <!-- Icons and User Profile -->
            <div class="icon-section d-flex align-items-center">
              <i class="bi bi-moon me-3"></i>
              <i class="bi bi-bell me-3"></i>
              <div class="d-flex justify-content-between">
              <div>
              <img src="@/assets/se.svg" alt="Flag" class="icon me-3"  style="margin-left: 50px;"/>
              <img src="@/assets/bar.svg" alt="Icon" class="icon me-3" style="margin-left: auto;" />
             </div>
             <div>
              <img src="@/assets/j.svg" alt="Icon" class="icon me-3" />
              <img src="@/assets/k.svg" alt="Icon" class="icon me-3" />
              <img src="@/assets/l.svg" alt="Icon" class="icon me-3" />
            </div>
           </div>

              

              <!-- Dropdown Button -->
              <button
                class="btn btn-secondary btn-sm dropdown-toggle text-dark"
                type="button"
                data-bs-toggle="dropdown"
                aria-expanded="false"
                style="background-color: white; border-style: none;"
              ></button>
            </div>
          </div>

          <div class="chat-header d-flex justify-content-between align-items-center p-2">
            <h5 class="mb-0">Chat</h5>
            <div class="d-flex align-items-center">
              <i class="bi bi-bell me-2"></i>
              <img src="../assets/ho.svg" alt="">
              <img src="../assets/slach.svg" alt="">
              <button class="btn text-primary btn-sm" style="background-color: #DDDBFF;">Chat</button>
            </div>
          </div>

          <!-- Create a horizontal row for contact list, media files, and chat container -->
          <div class="d-flex flex-row justify-content-between p-3">
            <div class="contact-list" style="flex: 1; margin-right: 15px;">
              <div class="profile d-flex align-items-center mb-4">
                <img src="../assets/face1.svg" alt="Mathew Anderson" class="rounded-circle me-3" width="50" height="50">
              </div>
              <div>
                <img src="../assets/face2.svg" alt="">
                <img src="../assets/face3.svg" alt="">
                <img src="../assets/face4.svg" alt="">
                <img src="../assets/face5.svg" alt="">
                <img src="../assets/face6.svg" alt="">
                <img src="../assets/face7.svg" alt="">
                <div>
                  <h5 class="m-0">{{ userProfile.name }}</h5>
                  <small class="text-muted">{{ userProfile.position }}</small>
                </div>
                <div class="ms-auto">
                  <i class="bi bi-three-dots-vertical"></i>
                </div>
              </div>

              <div class="search mb-3">
                <div class="input-group">
                  <span class="input-group-text bg-light border-0">
                    <i class="bi bi-search"></i>
                  </span>
                  <input type="text" class="form-control border-0" placeholder="Search contacts">
                </div>
              </div>

              <div class="recent-chats">
                <h6 class="text-muted">Recent Chats</h6>
                <ul class="list-group">
                  <li v-for="chat in chats" :key="chat.name" class="list-group-item d-flex align-items-center border-0 py-3">
                      
                      <img src="../assets/face1.svg" alt="Mathew Anderson" class="rounded-circle me-3" width="50" height="50">
                    <div class="flex-grow-1">
                      <h6 class="mb-0">{{ chat.name }}</h6>
                      <small class="text-muted">{{ chat.message }}</small>
                    </div>
                    <small class="text-muted">{{ chat.time }}</small>
                  </li>
                </ul>
              </div>
            </div>

            <div class="chat-container" style="flex: 2; margin: 0 15px;">
              <div class="message" v-for="message in messages" :key="message.id">
                <div class="message-info d-flex align-items-center">
                  <img src="../assets/face1.svg" alt="Mathew Anderson" class="rounded-circle me-3" width="50" height="50">
                  <div>
                    <strong>{{ message.username }}</strong>
                    <span class="text-muted small">{{ message.time }}</span>
                  </div>
                </div>

                <div class="message-content mt-2" :class="message.type">
                  <p>{{ message.text }}</p>
                </div>
              </div>

              <div class="message-input-container d-flex align-items-center mt-3 justify-content-between p-3 border-top">
                  <div class="icon smile-icon me-3">
                  <img src="../assets/smile.svg" alt="icon"/>
                <input type="text" placeholder="Type a Message" class="form-control me-2">
              </div>
                <div class="icons d-flex align-items-center ms-3">
                <img src="../assets/tev.svg" alt="icon">
                <img src="../assets/hal.svg" alt="icon">
                <img src="../assets/maic.svg" alt="icon">
                </div>
              </div>
            </div>

            <div class="media-files-container" style="flex: 1; margin-left: 15px;">
              <div class="icons d-flex align-items-center mt-3">
            <i class="bi bi-slash-circle text-primary me-3" title="Block"><img src="../assets/stop.svg" /></i>
            <i class="bi bi-trash text-danger me-3" title="Delete"><img src="../assets/delet.svg" /></i>
            <i class="bi bi-telephone text-secondary me-3" title="Call"><img src="../assets/call.svg" /></i>
            <i class="bi bi-camera-video text-secondary me-3" title="Video Call"><img src="../assets/vedio.svg" /></i>
            <i class="bi bi-list text-secondary" title="More"><img src="../assets/travel.svg" /></i>
          </div>


          <hr>
              <div class="media-section mb-4">
                <h6 class="text-muted mb-3">Media (36)</h6>
                <div class="d-flex flex-wrap">
                  <img src="../assets/a.svg" alt="" class="rounded-circle me-3" width="50" height="50">
                  <img src="../assets/b.svg" alt="">
                  <img src="../assets/c.svg" alt="">
                  <img src="../assets/d.svg" alt="">
                  <img src="../assets/a.svg" alt="">
                  <img src="../assets/b.svg" alt="">
                </div>
              </div>

              <div class="files-section">
                <h6 class="text-muted mb-3">Files (36)</h6>
                <ul class="list-group">
                  <li v-for="file in files" :key="file.id" class="list-group-item border-0 d-flex align-items-center mb-2">
                      <img :src="file.image" alt="">
                    <div>
                      <h6 class="mb-0">{{ file.name }}</h6>
                      <small class="text-muted">{{ file.message }}</small>
                    </div>
                    <div class="ms-auto">
                      <i class="bi bi-three-dots-vertical"></i>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div v-if="showDialog" class="dialog-overlay" @click="closeDialog">
    <div class="dialog-content" @click.stop>
      <div class="dialog-header">
        <img :src="dialogIcon"  class="dialog-icon" />
        <h3 class="dialog-title">{{ dialogTitle }}</h3>
      </div>
      <p class="dialog-message">{{ dialogMessage }}</p>
      <div class="dialog-actions">
        <button class="btn-cancel" @click="closeDialog">Cancel</button>
        <button class="btn-confirm" @click="confirmAction">Yes</button>
      </div>
    </div>
    <div class="d-flex align-items-center">
    <a href="#" class="icon2" @click="openDialog('block')">
      <img src="../assets/stop.svg" class="me-1" alt="Block" />
    </a>
    <a href="#" class="icon2" @click="openDialog('delete')">
      <img src="../assets/delet.svg" class="me-1" alt="Delete" />
    </a>
    <a href="#" class="icon2" @click="openDialog('unlock')">
      <img src="../assets/unlock.svg" class="me-1" alt="unlock" />
    </a>
    <a href="#" class="icon2" >
      <img src="../assets/vedio.svg" class="me-1" alt="Clip" />
    </a >
    <a  href="#" class="icon2">
      <img src="../assets/travel.svg" class="me-1" alt="slid" />
    </a>
   
    <a  href="#" class="icon2">
      <img src="../assets/call.svg" class="me-1" alt="tele" />
    </a>
</div>
  </div>
  </section>
</template>

  <script>
  import image1 from '../assets/e.svg';
  import image2 from '../assets/f.svg';
  import image3 from '../assets/g.svg';
  import image4 from '../assets/h.svg';
  import image5 from '../assets/i.svg';
  

  export default {
    data() {
      return {
        userProfile: {
          name: 'Mathew Anderson',
          position: 'Marketing Director',
          image: '../assets/face1.svg/50' 
        },
        chats: [
          {
            name: 'Michell Flintoff',
            message: 'You: Yesterday was great...',
            time: '15 minutes',
            image: '../assets/face2.svg/40'
          },
          {
            name: 'Bianca Anderson',
            message: 'Nice looking dress you...',
            time: '30 minutes',
            image: '../assets/face3.svg/40'
          },
          {
            name: 'Andrew Johnson',
            message: 'Sent a photo',
            time: '2 hours',
            image: '../assets/face4.svg/40'
          },
          {
            name: 'Mark Strokes',
            message: 'Lorem ipsum text...',
            time: '5 days',
            image: '../assets/face5.svg/40'
          },
          {
            name: 'Mark, Stoinus & Rishvi..',
            message: 'Lorem ispusm text ...',
            time: '5 days',
            image: '../assets/face6.svg/40' 
          },
          {
            name: 'Bianca Anderson',
            message: 'Nice looking dress you...',
            time: '30 minutes',
            image: '../assets/face7.svg/40' 
          },
        ],
        messages: [
          {
            id: 1,
            username: 'Andrew',
            avatar: '../assets/poli.svg',
            time: '2 hours ago',
            text: "If I don't like something, I'll stay away from it.",
            type: 'received',
          },
          {
            id: 2,
            username: 'You',
            avatar: 'https://via.placeholder.com/40',
            time: '2 hours ago',
            text: "If I don't like something, I'll stay away from it.",
            type: 'sent',
          },
          {
            id: 3,
            username: 'Andrew',
            avatar: '../assets/poli.svg',
            time: '2 hours ago',
            text: "I want more detailed information.",
            type: 'received',
          },
          {
            id: 4,
            username: 'Andrew',
            avatar: 'https://via.placeholder.com/40',
            time: '2 hours ago',
            text: "They got there early, and they got really good seats.",
            image: '../assets/a.svg',
            type: 'received',
          },
        ],
  
        files: [
          {
            name: 'service-task.pdf',
            message: '2 MB  2 Dec 2022',
            image:image1
          },
          {
            name: 'homepage-design.fig',
            message: '2 MB  2 Dec 2022',
            image:image2
          },
          {
            name: 'about-us.html',
            message: '2 MB  2 Dec 2022',
            image:image3
          },
          {
            name: 'work-project.zip',
            message: '2 MB  2 Dec 2022',
            image: image4
          },
          {
            name: 'custom.js',
            message:'2 MB  2 Dec 2022',
            image:image5
          },
        ],
        
      };
    },
  };
  
  </script>
  
  <style>
  .sidebar {
    height: 100vh; /* يجعل السايد بار يمتلئ الشاشة */
    position: sticky;
    top: 0;
  }

  .chat-header {
    background-color: #f8f9fa;
  }

  .contact-list {
    border: 1px solid #e0e0e0;
    border-radius: 5px;
    padding: 15px;
    margin-top: 15px;
    background-color: white;
  }

  .media-files-container {
    border: 1px solid #e0e0e0;
    border-radius: 5px;
    padding: 15px;
    margin-top: 15px;
    background-color: white;
  }

  .chat-container {
    border: 1px solid #e0e0e0;
    border-radius: 5px;
    padding: 15px;
    margin-top: 15px;
    background-color: white;
  }

  .input-container {
    border-top: 1px solid #e0e0e0;
    padding-top: 10px;
  }

  .media-item {
    border: 1px solid #e0e0e0;
    border-radius: 5px;
    padding: 5px;
    width: 60px;
    height: 60px;
  }

  .message {
    margin-bottom: 15px;
  }

  .message-content {
    background-color: #f1f1f1;
    border-radius: 5px;
    padding: 10px;
  }

  .message-info {
    font-size: 12px;
  }

  .avatar {
    border-radius: 50%;
    width: 30px;
    height: 30px;
  }

  .text-muted {
    color: #6c757d;
  }

  .dialog-overlay {
position: fixed;
top: 0;
left: 0;
right: 0;
bottom: 0;
background-color: rgba(0, 0, 0, 0.5);
display: flex;
justify-content: center;
align-items: center;
z-index: 1000;
}

/* Dialog content */
.dialog-content {
background-color: white;
padding: 20px;
border-radius: 10px;
text-align: center;
width: 320px;
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

/* Dialog header */
.dialog-header {
display: flex;
flex-direction: column;
align-items: center;
margin-bottom: 20px;
}

/* Dialog icon */
.dialog-icon {
width: 40px;
height: 40px;
margin-bottom: 10px;
}

/* Dialog title */
.dialog-title {
font-size: 18px;
font-weight: 600;
margin: 0;
color: #333;
}

/* Dialog message */
.dialog-message {
font-size: 14px;
color: #666;
margin-bottom: 20px;
}

/* Dialog actions (buttons) */
.dialog-actions {
display: flex;
justify-content: space-between;
}

/* Cancel button */
.btn-cancel {
background-color: #ccc;
color: #333;
border: none;
padding: 10px 20px;
border-radius: 5px;
cursor: pointer;
font-size: 14px;
}

/* Confirm button */
.btn-confirm {
background-color: #635bff;
color: white;
border: none;
padding: 10px 20px;
border-radius: 5px;
cursor: pointer;
font-size: 14px;
}

.btn-cancel:hover, .btn-confirm:hover {
opacity:0.9;
}

</style>


