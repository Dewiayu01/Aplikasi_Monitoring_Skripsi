## install module

> npm install

## menjalankan server

> npm run dev

server berjalan pada url http://localhost:5001

## membuat database
> npx sequelize-cli db:create

## membuat model
> npx sequelize-cli model:generate --name User --attributes firstName:string,lastName:string,fullName:string

## migrasi model ke database
> npx sequelize-cli db:migrate

## rollback migrasi
> npx sequelize-cli db:migrate:undo --name [nama file migrasi pada folder migrations].js

## endpoint

> http://localhost:5001/admin/login

> http://localhost:5001/dosen/login

> http://localhost:5001/mahasiswa/login

> http://localhost:5001/koordinator-skripsi/login



- User
sequelize model:generate --name User --attributes username:string,email:string,password:string,role:

-studentUser
sequelize model:generate --name StudentUser --attributes npm:integer,nama:string,gender:string,angkatan:string,foto:string,username:string,email:string,password:string,role:string

- lecturerUser
sequelize model:generate --name LecturerUser --attributes nip:integer,nama:string,gender:string,foto:string,username:string,email:string,password:string,role:string


- coordinatorUser

sequelize model:generate --name CoordinatorUser --attributes nip:integer,nama:string,gender:string,foto:string,
username:string,email:string,password:string,role:string

FK ke DevifionOfLecturer
sequelize migration:generate --name add-StudentUserId-to-DevisionOfLecturer
sequelize migration:generate --name add-StudentUserId-to-TitleSubmission
sequelize migration:generate --name add-StudentUserId-to-TitleSubmission2
sequelize migration:generate --name add-StudentUserId-to-ThesisRegistration
sequelize migration:generate --name add-StudentUserId-to-Proposal
sequelize migration:generate --name add-LecturerUserId-to-Proposal
sequelize migration:generate --name add-LecturerUserId2-to-Proposal
sequelize migration:generate --name add-LecturerUserId3-to-Proposal
sequelize migration:generate --name add-LecturerUserId-to-StudentUser
sequelize migration:generate --name add-LecturerUserId2-to-StudentUser
sequelize migration:generate --name add-LecturerUserId3-to-StudentUser

sequelize migration:generate --name add-dosenPembimbing1Id-to-DevisionOfLecturer
sequelize migration:generate --name add-dosenPembimbing2Id-to-DevisionOfLecturer
sequelize migration:generate --name add-dosenPembahasId-to-DevisionOfLecturer
sequelize migration:generate --name add-DevisionOfLecturerId-to-Proposal

sequelize migration:generate --name add-ThesisRegistrationId-to-TitleSubmission
sequelize migration:generate --name add-ThesisRegistrationId-to-ThesisRegistration





list of lecturers
sequelize model:generate --name ListOfLecturer1 --attributes dosenPembimbing1:string
sequelize model:generate --name ListOfLecturer2 --attributes dosenPembimbing1:string
sequelize model:generate --name ListOfLecturer3 --attributes dosenPembahas:string

         <div class="form-group">
         <% dataBimbinganHasilSkripsi.map((item, i) => { %>
             <% if (item.DevisionOfLecturer) { %>
                 <% if (item.DevisionOfLecturer.dosenPembimbing1 === username) { %>
                 <label for="hasilSkripsiRevisiDosen1">Upload File Revisi 1 Bimbingan Hasil Skripsi 
Mahasiswa</label>
                 <input class="form-control-file" type="file" accept="*/*" 
name="hasilSkripsiRevisiDosen1" id="hasilSkripsiRevisiDosen1" required>
                 <% } else if (item.DevisionOfLecturer.dosenPembimbing2 === username) { %>
                 <label for="hasilSkripsiRevisiDosen2">Upload File Revisi 2 Bimbingan hasilSkripsi 
Mahasiswa</label>
                 <input class="form-control-file" type="file" accept="*/*" 
name="hasilSkripsiRevisiDosen2" id="hasilSkripsiRevisiDosen2" required>
                 <% } %>
             <% } %>
         <% }) %>
     </div>

