# Android-Studio-Practice-1
Пробный репозиторий. Старый проект "Таблица для учителя"
```
private void btnAdd_Click(object sender, EventArgs e)
        {
            string[] student = new string[4];

            student[0] = (dataGridView1.Rows.Count + 1).ToString();
            student[1] = textBoxFirstName.Text;
            student[2] = textBoxSecondName.Text;
            student[3] = textBoxRating.Text;

            dataGridView1.Rows.Add(student[0], student[1], student[2], student[3]);
        }

        private void btnDelete_Click(object sender, EventArgs e)
        {
            dataGridView1.Rows.Remove(dataGridView1.SelectedRows[0]);

            textBoxFirstName.Clear();
            textBoxSecondName.Clear();
            textBoxRating.Clear();
        }

        private void dataGridView1_CellClick(object sender, DataGridViewCellEventArgs e)
        {
            textBoxFirstName.Text = dataGridView1.SelectedRows[0].Cells[1].Value.ToString();
            textBoxSecondName.Text = dataGridView1.SelectedRows[0].Cells[2].Value.ToString();
            textBoxRating.Text = dataGridView1.SelectedRows[0].Cells[3].Value.ToString();
        }

        private void btnEdit_Click(object sender, EventArgs e)
        {
            string[] student = new string[3];

            student[0] = textBoxFirstName.Text;
            student[1] = textBoxSecondName.Text;
            student[2] = textBoxRating.Text;

            dataGridView1.SelectedRows[0].Cells[1].Value = student[0];
            dataGridView1.SelectedRows[0].Cells[2].Value = student[1];
            dataGridView1.SelectedRows[0].Cells[3].Value = student[2];
        }

        private void btnAverage_Click(object sender, EventArgs e)
        {
            int summ = 0;
            int count = dataGridView1.Rows.Count;

            if(count != 0)
            {
                for (int i = 0; i< count; i++)
                {
                    int rating = Convert.ToInt32(dataGridView1.Rows[i].Cells[3].Value);
                    summ += rating;
                }
                int average = summ / count;

                textBoxAverage.Text = average.ToString();
            }
        }
        ```
